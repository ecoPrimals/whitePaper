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

## K = [null] — No Key, No Door

### The problem with RustDesk wasn't the key. It was the DOOR.

RustDesk uses a cryptographic key. Key works (K=1) or doesn't
(K=0). Binary. A door with a lock. This is the wrong model.

```
KEY-BASED ACCESS (wrong model):
  K = 1 → door opens → full access
  K = 0 → door locked → no access
  Problem: someone gets the key → they get EVERYTHING
  Problem: the door EXISTS even when locked
  Problem: binary. all or nothing. capturable.

MEMBRANE ACCESS (right model):
  K = [null] → no key, no door, no lock
  Access is SELECTIVE PERMEABILITY
  Not "does the key fit?" but "does the shape bind?"
  Not binary. Contextual. Per-molecule. Per-moment.
```

### A membrane is not a wall with a door.

A cell membrane doesn't have doors. It has selective permeability.
Specific molecules pass based on SHAPE, CHARGE, SIZE, CONTEXT.
Not based on a key. An epitope is not a key — it's a binding site.
A key is binary (fits / doesn't). An epitope is contextual
(binds under THESE conditions, with THIS shape, at THIS
concentration, at THIS moment).

RustDesk on northGate was a DOOR with a KEY. Binary access.
Full remote desktop. K = {0, 1}. If anyone got the key, they
got everything. That's not a membrane — that's a wall with a
hole and a lock.

**K = [null] means: no keys. No doors. No locks. No mechanism
of binary access exists on this machine. What remains is
selective only.**

### What selective looks like on northGate:

| Channel | Type | Why it's membrane, not door |
|---------|------|---------------------------|
| Git push (SSH) | Selective | Passes git protocol ONLY. No shell. Specific repos. Shape-matched. |
| HTTP observe | Selective | Read-only. Same as any browser on earth. No auth. Public surface. |
| Physical disk | Selective | Kevin's hands. Physical presence. Cannot be remoted. |
| Cursor workspace | Selective | Local compute. Pushes through git channel. Doesn't open inward. |

None of these are doors. None have keys. None are binary.
They're membrane channels — selective, contextual, shape-based.

### What's been [NULL]ed:

| Was | Model | Now |
|-----|-------|-----|
| RustDesk relay | KEY (binary, capturable) | [NULL] — mechanism removed, not just key revoked |
| RustDesk config | KEY (stored secret) | [NULL] — config purged, not just rotated |
| Cross-membrane remote desktop | DOOR (full access tunnel) | [NULL] — door removed, not just locked |
| WAN relay bridge (.1.x ↔ .4.x) | DOOR (subnet bridge) | [NULL] — never installed on northGate |
| WireGuard enrollment | DOOR (mesh membership) | [NULL] — northGate not on inner mesh |

The point isn't "we locked the door better." The point is
**there is no door.** K = [null]. Not zero. Not one. Null.
The variable was never assigned. The concept doesn't apply.

**No key. No door. Selective only.**

---

## What northGate Is Not

- Not an experiment ground for unproven NUCLEUS patterns
- Not a Linux gate — all NUCLEUS primals target Linux first
- Not expected to run `membrane` or `gate.bootstrap` until Windows port exists
- Not on the same subnet as the other gates (WAN relay for remote access)
