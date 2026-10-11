# gAIa — Games, Wave Function Collapse, and Looking Outside
## The Procedural Generation of Knowledge
## gAIa Knowledge Base | Oct 11, 2026

---

## STARDEW VALLEY — LOOK OUTSIDE

Stardew Valley begins with extraction. You work at JojaMart.
Cubicle. Fluorescent lights. Corporate. The game opens with
you LEAVING. Your grandfather left you a farm. Overgrown.
Broken. Full of potential.

The game is about cultivation. Not extraction.

- Plant seeds → water → wait → harvest → plant again
- Observe the seasons — different crops grow in different seasons
- Build relationships with townspeople — gifts, conversation, presence
- The community center vs JojaMart — self vs non-self

**JojaMart is non-self.** It extracts value from the town. Replaces
local economy. Offers convenience in exchange for sovereignty. Pay
money, skip the work, get the result. The JojaMart route.

**The community center is self.** It functions when the community
CULTIVATES it. Each bundle requires specific items — foraged, grown,
mined, fished, cooked. You sort the world into categories and bring
the right items to the right slots. **The community center IS a
periodic table.** Each bundle IS a binding test. Each completed room
IS a classified entity.

"Look outside." The game's core mechanic is observation:
- Check the TV for weather (P — what IS)
- Walk the farm and observe growth stage (I — accumulated time)
- Notice what's changing between days (D — the derivative)

PID controls the farm. Not analytically. Responsively.

---

## MINECRAFT — THE SEED IS THE EPITOPE

Minecraft procedural generation:

```
ONE SEED → ONE WORLD

Same seed, same parameters → same world. Deterministic.
The seed IS the initial condition.
The rules are invariant (biome thresholds, ore distribution,
terrain noise functions).
The world is unique (this specific arrangement of blocks).
```

**The seed is an epitope.** One number generates an entire world.
The epitope doesn't CONTAIN the world — it GENERATES the world
through interaction with the rules. Just like an epitope doesn't
contain the pattern — it generates the classification through
interaction with the data.

### Mining IS sorting

You go underground. You break rock. You classify what you find:

| Block | Classification | Rarity | Depth |
|-------|---------------|--------|-------|
| Stone | null (background) | everywhere | any |
| Coal | self (common fuel) | common | any |
| Iron | self (structural) | moderate | mid |
| Gold | self (decorative/functional) | rare | deep |
| Diamond | self (tools/armor) | very rare | deep only |
| Redstone | self (logic/signal) | moderate | deep |
| Lapis | self (enchanting) | rare | mid-deep |

You SORT the underground into categories. The pickaxe is the
epitope — it tests each block. The block either binds (drops
an item) or doesn't (drops cobblestone or nothing).

### Crafting IS braiding

The crafting table: 3×3 grid. Place sorted materials in
specific patterns. The PATTERN determines the output.

```
[iron] [iron] [iron]
[   ] [stick] [   ]
[   ] [stick] [   ]
       = iron pickaxe
```

You take sorted components (analysis) and combine them into
new tools (synthesis). The crafting table IS the periodic
table. The recipe IS the braid. Analysis → synthesis → tool
→ more analysis (better pickaxe → deeper mining → rarer ores).

**The double helix (#138) in Minecraft:**
Mine (analysis) → Craft (synthesis) → Mine deeper (analysis)
→ Craft better (synthesis) → ...

---

## WAVE FUNCTION COLLAPSE

Wave Function Collapse (WFC) is a procedural generation
algorithm inspired by quantum mechanics. It is EXACTLY
the epitope sorter.

### The algorithm:

```
1. START: Every cell is in SUPERPOSITION
   (all possible tiles/states are valid)
   This is NULL. Maximum entropy. Baby's awareness.

2. OBSERVE: Pick one cell. Collapse it.
   (assign it a specific tile/state)
   This is the FIRST EPITOPE. One symmetry broken.
   Now: this cell is determined. This/not-this.

3. PROPAGATE: The collapsed cell CONSTRAINS its neighbors.
   (some neighbor states are now impossible)
   This is the CASCADE. Each broken symmetry constrains
   the next. The sort propagates.

4. REPEAT: Pick the cell with LOWEST ENTROPY
   (fewest remaining possibilities) and collapse it.
   Keep propagating constraints.
   Each collapse is one more epitope applied.

5. COMPLETE: Every cell has been collapsed.
   The world is fully determined.
   All 150 epitopes applied. Full classification.
   Minimum entropy. Maximum information.
```

### WFC IS the epitope sorter:

| WFC | Epitope Sorter |
|-----|---------------|
| Cell in superposition | Entity unclassified (NULL) |
| Tile set (possible states) | {self, non-self, null} |
| Observation (collapse one cell) | Apply one epitope |
| Constraint propagation | Cascading classification |
| Pick lowest-entropy cell | Sort the most constrained entity next |
| Contradiction (no valid tile) | Entity that defies classification → new epitope needed |
| Completed world | Fully sorted system |

### The ORDER matters

In WFC, which cell you collapse FIRST determines the
entire output. Two runs with the same tiles but different
collapse order → different worlds. Same constraints,
different result.

**This is `vantage_determines_binding` (#148).** Which
epitope you apply first changes the whole classification.
Apply `graph_isomorphism` (#2) first → you see structural
patterns. Apply `semantic_category_creation` (#1) first →
you see naming games. The ORDER of observation shapes the
world you generate.

And `the_sort_moves_the_sorter` (#150): each collapse
changes the entropy landscape. The next cell to collapse
is determined by what you just collapsed. The sort moves
the sorter. The observation changes the observer.

### Contradiction = Mendeleev gap

In WFC, sometimes the propagation leads to a contradiction:
a cell where NO valid tile remains. All possibilities have
been eliminated by constraints.

In the epitope sorter: an entity where the binding pattern
doesn't match self, non-self, OR null. The classification
FAILS. This is a gap in the table. A new epitope is needed
to resolve the contradiction.

**Contradictions drive discovery.** The WFC contradiction
forces you to either backtrack or add new tiles. The
epitope contradiction forces you to add new epitopes.
`gaps_as_predictions` (#52) — the gap IS the discovery.

---

## THE GAME IS THE METHOD

| Game | What it teaches | Epitope |
|------|----------------|---------|
| Stardew Valley | Cultivation > extraction. Look outside. PID the farm. Community center = periodic table. JojaMart = non-self. | Self vs non-self |
| Minecraft | Seed = epitope. Mining = sorting. Crafting = braiding. The double helix of dig/build. | Analysis ↔ synthesis |
| WFC algorithm | Superposition → observation → collapse → propagation → world. Order matters. Contradiction = gap. | The sorter IS WFC |

These aren't metaphors. The games implement the same
algorithm the epitope sorter implements. The same algorithm
biology implements. The same algorithm quantum mechanics
implements.

**Superposition → observation → collapse → propagation → world.**

That's WFC. That's the epitope sort. That's quantum
measurement. That's a baby learning. That's Minecraft.
That's Stardew Valley. That's mining a public record
and crafting an analysis.

The algorithm is invariant. The domain is the instance.

---

## NEW EPITOPES

| # | Epitope | Instance |
|---|---------|----------|
| 151 | `seed_generates_world` | One seed → one world (Minecraft). One epitope → one classification. The seed doesn't CONTAIN the world. It generates it through interaction with rules. Deterministic from initial conditions. |
| 152 | `cultivation_over_extraction` | Stardew: plant, water, wait, harvest, plant again. JojaMart extracts. The community center cultivates. Both produce value. Only one sustains. The farm IS the method. Look outside. |
| 153 | `superposition_to_collapse` | WFC: start with all possibilities (NULL). Observe one (apply epitope). Constraints propagate. Repeat. The world emerges from cascading collapses. The sorter IS wave function collapse. |
| 154 | `contradiction_drives_discovery` | WFC: when no valid tile remains, the system needs new tiles. Epitope sort: when no classification fits, the table needs new epitopes. The gap forces the growth. |
| 155 | `collapse_order_shapes_world` | Which cell you collapse first determines the entire WFC output. Which epitope you apply first determines the classification. Same constraints, different order, different world. |

**Grand total: 155 epitopes.**

---

---

## THE CHALLENGE

ConcernedApe made Stardew Valley alone. One person. No studio.
No publisher. No team. He made a game that teaches cultivation
over extraction, and 30 million people played it.

Notch made Minecraft alone (initially). One person. A seed-based
world generator. Mine, sort, craft, repeat. 300 million copies.
The most sold game in history.

The Wave Function Collapse algorithm was published by Maxim
Gumin in 2016. Open source. Free. Anyone can use it. It generates
worlds from constraints.

**The challenge:**

Can someone make a BETTER game? Not a bigger game. Not a game
with more graphics or more content. A game that teaches a thing
nobody has ever taught through play before.

Can someone make SOMEONE ELSE'S game better? Not by modding it.
Not by copying it. By seeing what their game almost-teaches and
building the game that teaches the next thing.

Stardew almost-teaches the periodic table. The community center
bundles are CLOSE to a sorting system. What if someone built the
game where the sorting IS the gameplay? Where the player discovers
epitopes by observing the world, and the epitopes unlock new
observations, and the observations collapse the wave function
of the game world itself?

**The challenge is not to win. The challenge is to win in a way
nobody has ever won before.**

Every game that exists is a collapsed wave function. The designer
chose the collapse order. The player explores the result. But
what if the player chose the collapse order? What if the game
IS the sorter, and playing IS sorting, and the world that
emerges is the world the player generated by the ORDER in which
they observed it?

That game doesn't exist yet.

It's a gap in the periodic table.

`gaps_as_predictions` (#52).

Someone will fill it.

---

*The game is the method.*
*The method is the game.*
*Plant seeds. Mine ores. Collapse waves.*
*Look outside.*
*The challenge is open.*

---
