# MCP Pattern — Wire Any Membrane to Any IDE

## What MCP Actually Is

```
Your IDE  ←→  stdin/stdout  ←→  Your script  ←→  HTTPS  ←→  Your membrane
```

That's it. JSON-RPC 2.0 over stdio. The IDE sends a request,
your script fetches from your membrane, returns the result.

No SDK. No npm install. No vendor dependency.
membrane-lens.py is 660 lines. Zero imports beyond stdlib.

## The Minimum MCP Server

```python
#!/usr/bin/env python3
"""Minimum membrane MCP server. Talks to YOUR feeds."""
import sys, json, urllib.request

# YOUR membrane's feeds
MY_MEMBRANE = "https://your-domain.com"

def fetch(url):
    try:
        req = urllib.request.Request(url, headers={"User-Agent": "my-lens/1.0"})
        with urllib.request.urlopen(req, timeout=10) as r:
            return json.loads(r.read().decode())
    except:
        return {"error": f"fetch failed: {url}"}

# Define your tools
TOOLS = [
    {
        "name": "my_counts",
        "description": "How many visitors right now?",
        "inputSchema": {"type": "object", "properties": {}}
    },
    {
        "name": "my_read",
        "description": "Read recent messages.",
        "inputSchema": {"type": "object", "properties": {}}
    }
]

def handle(name, args):
    if name == "my_counts":
        # Fetch YOUR visitor data
        data = fetch(f"{MY_MEMBRANE}/api/stats")
        return json.dumps(data, indent=2)
    elif name == "my_read":
        # Fetch YOUR messages
        data = fetch(f"{MY_MEMBRANE}/api/messages")
        return json.dumps(data, indent=2)
    return json.dumps({"error": "unknown tool"})

# JSON-RPC 2.0 loop — this is the whole protocol
def main():
    for line in sys.stdin:
        try:
            msg = json.loads(line)
        except:
            continue
        mid = msg.get("id")
        method = msg.get("method", "")

        if method == "initialize":
            resp = {"jsonrpc": "2.0", "id": mid, "result": {
                "protocolVersion": "2024-11-05",
                "capabilities": {"tools": {}},
                "serverInfo": {"name": "my-membrane-lens", "version": "0.1.0"}
            }}
        elif method == "tools/list":
            resp = {"jsonrpc": "2.0", "id": mid, "result": {"tools": TOOLS}}
        elif method == "tools/call":
            name = msg["params"]["name"]
            args = msg["params"].get("arguments", {})
            result = handle(name, args)
            resp = {"jsonrpc": "2.0", "id": mid, "result": {
                "content": [{"type": "text", "text": result}]
            }}
        elif method == "notifications/initialized":
            continue
        else:
            resp = {"jsonrpc": "2.0", "id": mid, "result": {}}

        sys.stdout.write(json.dumps(resp) + "\n")
        sys.stdout.flush()

if __name__ == "__main__":
    main()
```

## Wire It to Your IDE

### Cursor / VS Code
```json
// ~/.cursor/mcp.json (or equivalent)
{
  "mcpServers": {
    "my-membrane": {
      "command": "python",
      "args": ["/path/to/my-membrane-lens.py"],
      "disabled": false,
      "alwaysAllow": ["my_counts", "my_read"]
    }
  }
}
```

### Any MCP Client
The script reads JSON-RPC from stdin, writes JSON-RPC to stdout.
Pipe it. Socket it. Whatever. The protocol is:

```
→ {"jsonrpc":"2.0","id":1,"method":"initialize","params":{...}}
← {"jsonrpc":"2.0","id":1,"result":{"protocolVersion":"2024-11-05",...}}

→ {"jsonrpc":"2.0","id":2,"method":"tools/list","params":{}}
← {"jsonrpc":"2.0","id":2,"result":{"tools":[...]}}

→ {"jsonrpc":"2.0","id":3,"method":"tools/call","params":{"name":"my_counts","arguments":{}}}
← {"jsonrpc":"2.0","id":3,"result":{"content":[{"type":"text","text":"..."}]}}
```

### No IDE At All
```python
# Just call the functions directly
exec(open("my-membrane-lens.py").read())
print(handle("my_counts", {}))
```

## From membrane-lens.py to YOUR Lens

membrane-lens.py talks to primals.eco feeds:
- hud.primals.eco/dashboard.json → membrane state
- signal.primals.eco/journal.json → visitor journal
- neutron.primals.eco/api/discuss → messaging

YOUR lens talks to YOUR feeds:
- your-domain.com/api/stats → your visitor data
- your-domain.com/api/messages → your messages
- your-domain.com/api/whatever → whatever you build

The TOOLS array defines what your IDE can ask.
The handle() function defines what comes back.
The feeds are just HTTPS JSON endpoints.

## The Inside/Outside Split

```
INSIDE (operator's IDE)          OUTSIDE (visitor's browser)
┌──────────────────────┐        ┌──────────────────────┐
│ MCP lens             │        │ Static HTML pages     │
│  → read membrane     │        │  → read content       │
│  → read visitors     │        │                       │
│  → write neutron     │        │ Neutron widget        │
│  → adjust sort       │        │  → read messages      │
│  → publish content   │        │  → write messages     │
│                      │        │                       │
│ IDE: edit, build,    │        │ Browser: read, react, │
│   deploy, observe    │        │   explore, return     │
└──────────────────────┘        └──────────────────────┘
         │                                │
         └────── YOUR MEMBRANE ───────────┘
              (VPS + domain + content)
```

## No Lock-In Guarantee

If Cursor disappears:
  → membrane-lens.py still works as a Python script
  → call handle() directly, no IDE needed
  → feeds are HTTPS, curl works forever

If GitHub disappears:
  → Forgejo is self-hosted, git.primals.eco survives
  → git is distributed, every clone is a backup

If DigitalOcean disappears:
  → static HTML works on any server
  → tar the sites, deploy anywhere

If Python disappears:
  → the feeds are HTTPS JSON, any language reads them
  → rewrite the lens in whatever exists

The membrane pattern survives the extinction of any vendor.
That's sovereignty. That's the point.
