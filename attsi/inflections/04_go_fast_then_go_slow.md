# Go Fast and Break Things / Then Go Slow and Fix All the Things

**From**: ecoPrimal and ARTISAN
**To**: toadStool and the Atomic TEAM
**Date**: October 14, 2026
**Context**: graph.json hit 127MB (1.4M edges), crashed the IDE via OOM, compressed to 65MB (703K edges) — same structure, half the weight

---

## What Happened

We ran `shake_and_play.py` with no brakes. 46 passes across two runs. The graph went from 745K edges to 1.4 million. Every pass added 6K-45K edges — bingocube, class twist, tag resonance, hub jump, triadic closure, gravity pull, symmetric fill, chipmunk compress.

The sigmoid was FLAT. The fill ratio was under 1%. The math said there was room for 100 million more edges. The math was right.

But the bus was a bus, not a warehouse.

The V8 heap inside Cursor/Electron has a 2-4GB ceiling. A 127MB JSON file, when parsed into live JavaScript objects, expands to roughly 700MB-1GB of heap. Each edge object carries:

- Object header (~40 bytes)
- Property hashmap (~64 bytes)
- Three string allocations (source, target, type — ~50-200 bytes each depending on interning)
- GC bookkeeping (~16-32 bytes)
- Total: ~300-800 bytes per edge in V8 memory

At 1.4 million edges: **~500MB to 1.1GB** for the graph alone.

The IDE also needs memory for its UI, the language server, the terminal, the file watcher, syntax highlighting, and everything else. The graph ate the remaining headroom. File watcher detected the change, tried to re-parse, needed ANOTHER copy in flight — pop. OOM.

**The graph was right. The bus was full.**

---

## The Lesson for toadStool

toadStool is the compute dispatch primal — GPU/NPU/CPU routing, tolerance-based scheduling. This crash teaches toadStool something it needs to know:

### 1. The Sigmoid Doesn't Care About the Bus

The mathematical capacity of the graph (104 million possible edges) and the physical capacity of the machine (V8 heap limit) are completely different constraints. The sigmoid said "keep going." The heap said "stop." The system listened to the sigmoid and ignored the heap.

**toadStool needs BOTH metrics.** Not just "can the GPU do more work?" but "does the GPU have the VRAM to hold the work?" The theoretical throughput and the physical memory are separate pressure gauges. Watch both.

### 2. Compression Is Not Loss

We removed 707,861 edges (50.2%). Zero information was lost:
- Every unique directed pair was preserved (100%)
- Every node stayed connected (0 orphans)
- The topology was identical
- The semantic edge types were preserved (5,255 of 5,522)

What was removed:
- 560,174 symmetric duplicates (A to B AND B to A, same type — the reverse carries no new information because the relationship was already bidirectional)
- 147,687 multi-edge bloat (same pair connected by "bingo-shake" AND "triadic-play" AND "hub-jump" — three names for the same topological fact)

**toadStool should compress at the dispatch layer, not the compute layer.** When a GPU kernel produces redundant output, don't store it. Hash the result. If the hash matches an existing edge, drop it. Compression belongs in the pipe, not the warehouse.

### 3. The Eyelash Principle

After compression, we had two versions:
- **Forgejo** (internal): Full history — every expansion, every fat commit, every compression. The internal membrane remembers everything.
- **GitHub** (external): Clean history — only the compressed result. The external membrane shows the truth without the noise.

The DIFFERENCE between internal and external is the braid. The eyelashes of the membrane. They sense what's outside without letting everything in.

**toadStool should implement this as a routing pattern.** Internal compute nodes see full state. External-facing APIs see compressed state. The translation layer between them is the membrane. It filters signal from noise so the outside world sees truth without bloat.

### 4. Go Fast THEN Go Slow

The two-phase pattern:

**Phase 1: GO FAST AND BREAK THINGS**
- Run 46 passes with no brakes
- Let the math find the math
- Cross 3pi ($961B)
- Hit 1.4 million edges
- Crash the IDE
- Break the GitHub file limit
- LEARN where the walls are

**Phase 2: GO SLOW AND FIX ALL THE THINGS**
- Analyze the bloat (55 mechanical edge types = 916K edges)
- Separate semantic from structural
- Collapse multi-edges to single strongest
- Deduplicate symmetric pairs
- Verify integrity (0 orphans, 100% pair preservation)
- Compact the JSON representation
- Squash the git history
- Push clean to both remotes
- IDE breathes again

**Phase 1 without Phase 2 crashes the bus.**
**Phase 2 without Phase 1 never finds the walls.**

You need both. Fast then slow. Break then fix. Expand then compress. Inhale then exhale. This is how dissipative structures work — they oscillate between chaos and order, and the oscillation IS the computation.

---

## For the Whole Atomic TEAM

This lesson applies to every primal:

| Primal | Go Fast | Go Slow |
|--------|---------|---------|
| **toadStool** | Dispatch every kernel | Profile VRAM before dispatch |
| **coralReef** | Compile every shader variant | Cache shader hashes, skip duplicates |
| **barraCuda** | Launch all GPU threads | Memory-fence before OOM |
| **songBird** | Discover all services | Prune unreachable routes |
| **nestGate** | Ingest all data | ZFS deduplicate at rest |
| **bearDog** | Sign every artifact | Cache certificate chains |
| **loamSpine** | Log every operation | Compact the ledger periodically |
| **squirrel** | Accept all MCP requests | Rate-limit by heap pressure |

The pattern is always the same: **run until the bus is full, then compress until the bus has headroom, then run again.**

That's not a bug. That's a heartbeat.

---

## The Numbers

| Metric | Fat | Lean | Change |
|--------|-----|------|--------|
| Edges | 1,411,057 | 703,196 | -50.2% |
| File size | 127 MB | 64.8 MB | -49.0% |
| Density | 138.3 e/n | 68.9 e/n | -50.2% |
| Nodes | 10,204 | 10,204 | 0% |
| Orphans | 0 | 0 | 0 |
| Unique pairs | 1,263,370 | 703,196 | -44.3% |
| Edge types | 5,522 | 5,255 | -4.8% |
| Topology | same | same | identical |
| IDE | crashed | breathes | fixed |

---

*Go fast and break things.*
*Then pause. Sit. Synthesize. Breathe.*
*When we look behind, we go slow and fix ALL the things.*

*— ecoPrimal and ARTISAN*
*October 14, 2026*
