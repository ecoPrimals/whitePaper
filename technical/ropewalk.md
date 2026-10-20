# The Ropewalk — Git as Braid Anchor

**Author:** Kevin Mok — ORCID 0009-0004-2141-0321  
**Date:** 2026-10-20  
**Wave:** 193

## The Craft

In the 17th century, rope makers worked in long buildings called **ropewalks** — some over 300 meters long. The maker walked backwards down the hall, feeding hemp strands through a twisting mechanism anchored at the far end. Each strand alone was weak. Twisted together, they became rope. The rope held ships to docks, anchors to the sea floor, sails to masts.

The ropewalk had three essential parts:
1. **The anchor** — a fixed point where the twist begins
2. **The strands** — individual fibers fed into the twist
3. **The walk** — the distance over which the twist propagates

The longer the ropewalk, the longer the rope. The more strands, the stronger the rope. The tighter the twist, the more the strands locked together.

## Git Is a Ropewalk

```
anchor          strands              the walk
  │               │                    │
  ▼               ▼                    ▼
initial       each commit           the timeline
commit        is a strand           is the ropewalk
(genesis)     fed into              (300 meters of
               the twist             commit history)
```

| Ropewalk | Git | The Membrane |
|----------|-----|-------------|
| **Anchor peg** | Initial commit (signed, hashed) | The genesis: `986160f` wave 193 start |
| **Strands** | Each commit (a diff, a change, a fact) | 30+ commits this wave, each a fiber |
| **The twist** | The hash chain (each commit references parent) | SHA-256 links every strand to the one before |
| **The walk** | The timeline (commit log, 71+ hours) | The ropewalk IS the wave |
| **The rope** | The branch (main, braided from strands) | The investigation, braided from evidence |
| **Rope strength** | Merge commits (multiple strands join) | Multiple artisans braid together |
| **The dock** | The deployment (GitHub Pages, detroit.primals.eco) | Where the rope HOLDS something |

## The Fuse

A rope is also a fuse. In the old world, a slow match was a rope soaked in saltpeter — it burned at a predictable rate. The fuse connected the flame to the cannon. The wicking allowed fire to travel along the cord at a controlled speed.

**Git is the fuse that connects reality to the internet.**

```
reality                    the fuse (git)              the internet
  │                           │                           │
  ▼                           ▼                           ▼
a fact exists              a commit captures it        the page displays it
(public record,            (timestamped, hashed,       (github.io, detroit,
 court filing,              signed, immutable)          sporeprint)
 FOIA response)
```

The fact exists in reality. The commit captures it in git. The deployment displays it on the internet. The fuse burns from reality → git → internet at the speed of `git push`.

Without git, the fact exists but has no fuse. It cannot travel. It cannot reach the internet. The ropewalk gives it a path.

## The Cycle

The rope maker walks **backwards** — facing the anchor, not the future. Each strand is added by looking at what came before, not what comes next. The twist propagates from the past toward the present.

Git works the same way: each commit looks backward (references its parent hash). The chain grows backward. The present commit knows the past. The past commit does not know the future.

**But the rope is used FORWARD** — it holds the ship to the dock, the anchor to the sea floor. The rope was made by walking backward but it is used by pulling forward.

The investigation works this way:
- The evidence is gathered by looking **backward** (public records, court filings, FOIA from the past)
- The investigation is used **forward** (legal action, public awareness, systemic change in the future)
- Git is the ropewalk that converts backward-looking evidence into forward-pulling rope

## The Braid

A rope is a braid. Three or more strands twisted together. The SweetGrass provenance braid in the membrane IS this — PROV-O braids that record what came from where, who touched it, how it was transformed.

The git commit graph IS the braid. Each branch is a strand. Each merge is a twist point. The braid's strength comes from the twist — you cannot pull one strand free without unraveling the others.

**The AGPL is the twist.** Without the license, the strands are loose fibers anyone can take. With the AGPL, the strands are twisted together — you can use the rope, but you cannot unravel it. The copyleft IS the twist that makes individual strands into collective rope.

## Alignment

The ropewalk aligns fibers that were random into a structure that has direction. Before the ropewalk, hemp fibers go everywhere. After the ropewalk, they all pull in the same direction.

Git aligns commits that were individual into a history that has direction. Before git, the evidence is scattered files. After git, the evidence is a timeline with provenance, hashes, signatures, and immutable ordering.

**The internet is the ocean.** The rope connects the ship (the investigation) to the anchor (the evidence). Without the rope, the ship drifts. Without git, the investigation has no anchor.

Like rope makers of old: we walk backward through the evidence, feeding each strand through the twist, and the rope grows. The rope holds. The ship does not drift.

```
banana_pi = 3.14159265358979
the rope is circular. π is the ratio of circumference to diameter.
the ropewalk is the diameter. the rope, when coiled, is the circumference.
C / d = π. the ropewalk / the rope = π.
the walk IS the pi of the work.
```

---

*Walk backward. Feed the strand. The twist holds. The rope grows. The ship stays.* 🪢🍌π
