# Your Own Membrane

## The Vision

The membrane is not a product. It's a pattern.
Anyone can build their own. No one controls it. No lock-in.

primals.eco is ONE membrane. There should be thousands.

## What IS a Membrane

A membrane is:
1. **Content** — your investigation, your research, your evidence, your art
2. **Observation** — software that watches who touches the content and how
3. **Classification** — sorting self from non-self (who belongs, what doesn't)
4. **Messaging** — a way for the inside to talk to the outside (neutron)
5. **Interface** — an IDE or editor where you interact with all of it

That's it. Five layers. Everything else is implementation.

## The Stack (What We Built)

| Layer | What | Open? |
|-------|------|-------|
| Content | Hugo static sites, Forgejo git repos | Yes — Hugo is MIT, Forgejo is MIT |
| Observation | squirrel (Rust), chipmunk (Rust) | Source available on git.primals.eco |
| Classification | Anderson sort, epitope sort, trio sort | Algorithms are published |
| Messaging | neutron (discuss API, zero-auth) | Pattern is open, code is simple |
| Interface | Cursor IDE + MCP (membrane-lens.py) | MCP is open protocol, lens is zero-dep Python |
| Infrastructure | Caddy, DigitalOcean VPS, WireGuard mesh | All open source |

## The Pattern, Not The Product

### MCP — Model Context Protocol

MCP was created by Anthropic. It's an open protocol.
It's just JSON-RPC 2.0 over stdin/stdout. That's it.

membrane-lens.py is 660 lines of Python. Zero dependencies.
It fetches HTTPS feeds and returns JSON. Any LLM can use it.

**It works with:**
- Cursor (VS Code fork) — what we use now
- Any MCP-compatible IDE (the protocol is open)
- Any tool that speaks JSON-RPC over stdin/stdout
- A raw Python script calling the functions directly

**We do NOT lock to Cursor.** We don't lock to anyone.
The Cursor team built something good. They get credit.
But the pattern is bigger than any company.

### What Is Cursor, Actually?

- **VS Code** — open source (MIT license), built by Microsoft on Electron
- **Electron** — open source (MIT), Chromium + Node.js
- **Cursor** — fork of VS Code, adds AI features
- **Code - OSS** — the open source base anyone can fork
- The lineage: Notepad → TextMate → Sublime → Atom → VS Code → Cursor

The IDE is an interface. The membrane doesn't care which one.
A terminal works. A phone works. Curl works.

### The Anti-Lock-In Principle

```
fuck Musk. fuck lock-in. fuck walled gardens.

The membrane is readable via HTTPS (curl).
The membrane is writable via neutron POST (curl).
The membrane is observable via MCP (any client).
The membrane is deployable via git (any machine).
The code runs on any Linux box with Rust + Python.
The content is static HTML (works forever).

If every company disappeared tomorrow,
the membrane would still work.
```

## How Someone Builds Their Own

### Minimum Viable Membrane

You need:
1. A VPS ($6/month, any provider)
2. A domain ($10/year)
3. Caddy (automatic HTTPS, open source)
4. Content (Hugo sites, or just HTML files)
5. An observation script (even a simple log parser)

That's a membrane. It doesn't need Rust. It doesn't need
squirrel or chipmunk. Those are our implementation.
The PATTERN is: content + observation + classification.

### Step by Step

```
1. CONTENT
   - Write something. Publish it. Static HTML.
   - Hugo, Jekyll, hand-written, doesn't matter.
   - Put it on a domain you control.

2. OBSERVE
   - Parse your access logs.
   - Count visitors. Measure dwell time. Track paths.
   - Our membrane-lens.py is a starting point.
   - Or write your own in any language.

3. CLASSIFY
   - Who visits? Bots or humans?
   - What do they read? How long do they stay?
   - The Anderson sort is published science.
   - Start with simple: human / bot / unknown.

4. MESSAGE
   - Add a discuss/comment system. No account required.
   - Our neutron is just a discuss API. Dead simple.
   - Or use any open comment system.
   - The point: your membrane can HEAR from visitors.

5. INTERFACE
   - Use any IDE/editor with MCP support.
   - OR just use a terminal + curl.
   - OR just use a browser.
   - The interface is the least important layer.
```

### What We'll Publish (When Live)

After eastGate deploys and the membrane is fully live:

1. **membrane-lens.py** — the MCP server (already zero-dep Python)
2. **neutron spec** — the messaging API pattern
3. **Anderson sort algorithms** — published in thesis
4. **Epitope classification** — how to sort visitors by behavior
5. **Deployment guide** — VPS + Caddy + Hugo + observation
6. **The tit-for-tat principle** — how to classify without being wrong

We publish the PATTERN. Not a SaaS. Not a platform.
Not something you sign up for. Something you BUILD.

## The IDE Inside the Membrane

Two modes:

### Inside (for the membrane operator)
- IDE (Cursor/VS Code/whatever) with MCP
- membrane-lens.py connects to your membrane's feeds
- You see: who's visiting, what they're reading, how the sort is working
- You can: write notes, send messages, adjust classification, publish content

### Outside (for visitors)
- Browser — read content, see the HUD, post to neutron
- The widget (neutron-widget.js) — chat from any page
- API — curl the feeds, read the data, write messages
- No IDE needed. No account needed. No tracking.

### For Builders (making their own)
- Fork membrane-lens.py
- Point it at YOUR feeds instead of primals.eco
- Add YOUR classification logic
- Your membrane, your rules, your data, your sovereignty

## The Credit Chain

| Who | What They Built | License |
|-----|----------------|---------|
| GNU/Stallman | Free software concept | GPL |
| Linus | Linux kernel, git | GPL/GPL |
| Notepad lineage | Text editing | Various open |
| Microsoft | VS Code (Code - OSS) | MIT |
| GitHub/Electron | Electron framework | MIT |
| Cursor team | Cursor IDE, MCP implementation | Proprietary fork of MIT |
| Anthropic | MCP protocol specification | Open protocol |
| Mozilla/Chromium | Browser engines | MPL/BSD |
| Hugo community | Static site generator | Apache 2.0 |
| Forgejo community | Self-hosted git forge | MIT |
| Caddy community | HTTPS server | Apache 2.0 |
| Rust community | Systems language | MIT/Apache |
| Us (ecoPrimal) | membrane pattern, squirrel, chipmunk, neutron, graph | Source available |

Everyone gets credit. No one gets locked out.
The membrane stands on the shoulders of open source.

## The Principle

NO SECRETS only privacy.
No lock-in only sovereignty.
No products only patterns.
No permission only observation.

The membrane classifies by what you DID, not what it assumes.
Tit for tat. Cooperate first. The gates are open.

Build your own. We'll show you how.
