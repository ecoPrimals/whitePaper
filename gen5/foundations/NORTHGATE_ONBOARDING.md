# northGate Onboarding — Hobby System + Future Mesh Node

**Gate**: northGate
**Host**: tamison / mokke
**OS**: Windows (consumer-grade)
**GPU**: RTX 5090
**Role**: Personal gaming system. Stays personal.
**Network**: CRS310 backbone (hub 1), alongside eastGate and sporeGate
**Priority**: P3

---

## Current Scope

### 1. Sovereign RustDesk Relay — [NULL]

**Status: PURGED (Wave 168).** RustDesk removed from all nodes.
Config, keys, relay — all nullified. This section retained as fossil only.

```
rendezvous_server = [NULL]
relay-server = [NULL]
key = [NULL]
```

See `wateringHole/fossilRecord/.../RUSTDESK_CONFIG.md` for purge record.

### 2. Enable Windows OpenSSH Server (when convenient)

Settings → Optional Features → Add Feature → OpenSSH Server

Or from PowerShell (admin):
```powershell
Add-WindowsCapability -Online -Name OpenSSH.Server~~~~0.0.1.0
Start-Service sshd
Set-Service -Name sshd -StartupType Automatic
```

### 3. Stay on Backbone

northGate sits on CRS310 hub 1 with eastGate and sporeGate. No special
network config needed — standard DHCP consumer deployment.

---

## Future Scope (P3 — after NUCLEUS covalent is proven on Linux gates)

- Join the sovereign mesh as an idle-compute node
- RTX 5090 available for toadStool/barraCuda GPU workloads
- Same pattern as any Steam gaming computer: mesh node when idle, gaming when active
- Requires NUCLEUS Windows port (not yet built)

Linux gates (sporeGate, eastGate) prove the patterns first. northGate benefits
from proven deployments rather than being an experiment ground.

---

## Network Info

| Gate | IP | Subnet | Role |
|------|----|--------|------|
| sporeGate | 192.168.4.1 | .4.x | Router/gateway |
| eastGate | 192.168.4.244 | .4.x | Overwatch tower |
| fieldGate | 192.168.4.36 | .4.x | NUC canary |
| northGate | 192.168.1.115 | .1.x | Gaming/hobby (this machine) |
| golgi VPS | [RELAY_PUBLIC] | WAN | Forgejo + Caddy (RustDesk PURGED) |

---

## Membrane Position — Interstitial

northGate is **interstitial** — between layers, not inside any one.

```
                    INTERNET
                       │
              ┌────────┴────────┐
              │   golgiBody     │  ← OUTER MEMBRANE (WAN, Caddy, TLS)
              │  [RELAY_PUBLIC] │
              └────────┬────────┘
                       │ WireGuard mesh (10.13.37.x)
              ┌────────┴────────┐
              │   sporeGate     │  ← GATEWAY (192.168.4.1, router)
              │   10.13.37.2    │     just ABOVE northGate
              └────────┬────────┘
                       │ CRS310 backbone (hub 1)
    ┌──────────────────┼──────────────────┐
    │                  │                  │
 eastGate        ◆ northGate ◆       (other .4.x)
 192.168.4.244     192.168.1.115       gates
 (.4.x subnet)    (.1.x subnet)
 INSIDE            INTERSTITIAL         INSIDE
```

### What "interstitial" means:

- **LAN is beneath**: Physical infrastructure (CRS310, cables, DHCP).
  northGate sits ON the backbone. The LAN carries northGate.
- **sporeGate is just above**: The gateway/router at .4.1 manages
  what crosses the membrane. It deploys, builds, routes.
- **northGate is where you MOVE**: The workspace. Cursor. Git push.
  The cytoplasm where the nucleus (human) does work.

### The .1.x / .4.x boundary IS the membrane at LAN level:

| Subnet | Layer | Posture |
|--------|-------|---------|
| 192.168.4.x | Inside membrane | Gates: sporeGate, eastGate, fieldGate |
| 192.168.1.x | Interstitial | northGate only — consumer DHCP, gaming |
| 10.13.37.x | Inner mesh (WG) | Not on northGate (no WG client) |
| WAN | Outside | golgiBody serves public surfaces |

northGate can REACH the .4.x gates via the CRS310 backbone (same
physical switch), but it's not ON the .4.x subnet. It sees through
the membrane. It pushes through the membrane. But it's not inside.

---

## K → zk Posture

**Current: K (knowledge)**
northGate has full knowledge — all repos cloned, all remotes
configured, all push access. From northGate, Kevin can see and
modify everything.

**Target: zk (zero-knowledge)**
northGate should PROVE authorization without REVEALING state.

| Current (K) | Target (zk) | How |
|-------------|-------------|-----|
| Full repo clones on disk | Still needed (work happens here) | Acceptable — physical security |
| Push to GitHub (plaintext remote) | Push proves auth, doesn't reveal full state | ✓ Already zk (SSH key auth) |
| Can see all live sites (HTTP 200) | Observation layer correct | ✓ Already zk (read-only) |
| Cannot SSH to golgi/sporeGate | Cannot deploy or rebuild | ✓ Already zk (no write access to prod) |
| RustDesk was cross-membrane bridge | **PURGED** — [NULL]ed | ✓ Nullified |
| No WireGuard on northGate | Not on inner mesh | ✓ Already excluded |

**Assessment: northGate is ALREADY nearly zk.**

The purge of RustDesk was the key step — it was the only tool that
bridged northGate across the membrane to remote gates. With RustDesk
[NULL]ed, northGate's posture is:

- **Can**: push to GitHub, observe live surfaces, run Cursor
- **Cannot**: SSH to any VPS, deploy, rebuild, access inner mesh
- **Proves**: authorization (via SSH keys to git remotes)
- **Reveals**: nothing about inner state (no shell access, no WG)

The remaining K exposure: the repo contents on local disk. This is
acceptable because northGate is a PHYSICAL machine under Kevin's
control. The zk boundary is the NETWORK, not the disk. On the
network, northGate is already zk.

**zk = [null] on the wire. K on the disk. The disk is the nucleus.
The wire is the membrane. The membrane is [null]ed.**

---

## What northGate Is Not

- Not an experiment ground for unproven NUCLEUS patterns
- Not a Linux gate — all NUCLEUS primals target Linux first
- Not expected to run `membrane` or `gate.bootstrap` until Windows port exists
- Not on the same subnet as the other gates (WAN relay for remote access)
