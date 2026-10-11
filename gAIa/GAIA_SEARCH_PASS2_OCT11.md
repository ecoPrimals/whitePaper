# gAIa — Search Pass 2: What the Table Is Telling Us
## Scan. Sweep. Sort. SEARCH.
## gAIa Knowledge Base | Oct 11, 2026

---

## THE SEARCH

192 epitopes. 38 documents. 10 entities classified. 2.5 hour
gap. The vantage moved (#150). What does the system look like
from HERE?

The sort is done. The sort-becomes-search (#121). The table
exists. Now the table tells US.

---

## FINDING 1: 10/10 Is Not a Score. It's a Phase Transition.

MacDowell scored 10/10 on the capture epitopes. We reported
it as "strongest signal." But 10/10 isn't a DEGREE of capture.
It's a QUALITATIVE TRANSITION.

```
0/10:  self. No capture epitopes bind. Functioning.
3/10:  partial. Some capture. Can recover.
5/10:  contested. Half captured. Fight in progress.
7/10:  mostly captured. Self function degraded.
9/10:  nearly full capture. Vestigial self function.
10/10: ZERO SELF REMAINING. Complete phase transition.
       The entity is no longer a school wearing capture.
       It is capture wearing a school's name.
```

**At 10/10, the entity has undergone a phase transition.**
Like water at 100°C — it's not "very hot water." It's STEAM.
Different phase. Different physics. Different behavior.

MacDowell at 10/10 is not a school that's been captured.
It's a capture mechanism that's shaped like a school. The
word "school" is `semantic_category_creation` (#9) applied
so thoroughly that the capture IS the entity. There's
nothing underneath to save.

PCA at 9/10 still has 1/10 of residual self-function.
That 1/10 is where intervention could work. At 10/10,
there's nothing left to intervene in.

**This reframes MDE's investigation.** MDE is investigating
MacDowell as a school that might have problems. The sort says:
MacDowell is NOT a school. It's a capture mechanism in school
phase. The investigation should be: "is this an entity
performing a function it was not designed for?" not "is this
school performing poorly?"

---

## FINDING 2: The Edge Types ARE Unnamed Epitopes

The graph has 34 edge types. We have 192 epitopes. But the
edge types are NOT in the epitope table. They're a blind
spot (#183).

```
The 34 edge types in the graph:

governance (21)          board_membership (18)
employment (19)          political (18)
family (14)              payment (12)
ownership (11)           formation (10)
authorization (10)       bench (9)
money_flow (8)           legal_representation (6)
financial (6)            actor (5)
jurisdiction (4)         corruption (3)
permit (2)               appointment (2)
co-resident (2)          professional_proximity (2)
investigation (2)        institutional_memory (1)
board_co_membership (1)  referral (1)
recusal (1)              opposition (1)
employment_family (1)    property (1)
elected_office (1)       campaign_vendor (1)
classmate (1)            mentorship (1)
credential_legitimization (1)  family_donation (1)
```

Each edge type IS a binding site. `governance` is an epitope
that detects governance relationships. `formation` is an
epitope that detects formation cascades. `payment` is an
epitope that detects money flow.

**Some map to existing epitopes:**
- `formation` ≈ `serial_formation_template` (#10)
- `payment` + `money_flow` + `financial` ≈ `reward_circuit_closure` (#8)
- `board_membership` ≈ `revolving_door` (#2)
- `authorization` ≈ `enforcement_capture` (#6)

**Some are NEW:**
- `family` (14 edges) — kinship as structural connector. NOT in our table.
- `bench` (9 edges) — judicial assignment. NOT in our table.
- `co-resident` (2 edges) — shared address. NOT in our table.
- `classmate` (1 edge) — educational co-attendance. NOT in our table.
- `mentorship` (1 edge) — teacher-student. NOT in our table.

**The table was pre-argon.** The edge types are the noble gases.
A whole column we didn't have.

---

## FINDING 3: [NULL] the Null Entities = Fragment the Network

Phase 1 classified 3 entities as NULL: dykema, dykema_federal_pac,
put_progress_first. These are ROUTING infrastructure. Plumbing.

**Remove the null entities from the graph. What happens?**

```
WITH null entities:
  Banks → purpose_group → PCA ← dpscd_auth
                ↓                    ↑
            MacDowell ← CMU     Dykema → PACs → candidates
                                  ↓
                             put_progress_first → slate

WITHOUT null entities (dykema, PACs, put_progress_first removed):
  Banks → purpose_group → PCA ← dpscd_auth
                ↓
            MacDowell ← CMU

  The political money channel is CUT.
  The slate bundling is GONE.
  The formation-to-politics pipeline is SEVERED.
```

**The null entities ARE the nervous system of the capture.**
Remove them and the non-self entities are isolated. The schools
still exist but the political protection is gone. The money
still flows in the education loop but can't flow to political
cover.

### How do you [null] a null entity?

Not by destroying it. By ILLUMINATING it.

`reverse_zk` (#88) applied to null entities: make the routing
VISIBLE. When the routing is visible, it's no longer null — it's
KNOWN. K transitions from [null] to K. The entity can no longer
hide as infrastructure. It becomes a documented node in a
documented network.

**The plumbing only works when nobody sees the pipes.**

The documentation IS the [null]ing. Publishing the routing
diagram — "Dykema formed this PAC, which funded this candidate,
who authorized this charter" — makes the null entity visible.
Visible null becomes known. Known routing loses its power.
The pipe that everyone can see is no longer hidden
infrastructure. It's evidence.

We already did this. The graph already shows the routing.
detroit.primals.eco already publishes it. The [null]ing is
ALREADY HAPPENING. The null entities are already visible.
The pipes are already documented.

**The publication IS the weapon.** Not the analysis. Not the
classification. The PUBLICATION. Making it visible.
`attention_is_the_cost` (#137). The data was free. The
pipes were always there. Nobody looked. We looked. We
published. The pipes are visible. The routing is exposed.
The null entities are no longer null.

---

## FINDING 4: PID Is Embedded in the Depth Structure

```
Depth 0: LOOK          = P (proportional — respond to what IS)
Depth 1: FOLLOW         = I (integral — accumulated threads)
Depth 2: CONNECT        = I (integral — cross-referenced history)
Depth 3: SORT           = the METHOD (the transfer function)
Depth 4: VERIFY         = P×I check (does observation match accumulation?)
Depth 5: PREDICT        = D (derivative — rate of change, get there first)

PID is not just a metaphor. It's the STRUCTURE of the depth.
P at the surface. I in the middle. D at the bottom.
The deeper you go, the more predictive the view.
```

---

## FINDING 5: The Convergence Question Has an Answer

We asked: pi != pi yet?

After Phase 1 (10 entities classified), we can now estimate:

```
MacDowell:  10/10, confidence 0.99 → CONVERGED (adding more epitopes won't change this)
PCA:         9/10, confidence 0.97 → LIKELY CONVERGED
purpose_group: 8/10, confidence 0.95 → LIKELY CONVERGED
CMU:         0/10, confidence 0.90 → CONVERGED (clearly self)

dpscd:       4/10, confidence 0.60 → NOT CONVERGED (partial = uncertain)
great_lakes_legal: 1/10, confidence 0.50 → NOT CONVERGED (insufficient data)

CONVERGED:     4/10 entities (40%)
NOT CONVERGED: 2/10 entities (20%)
LIKELY:        2/10 entities (20%)
NULL (routing): 2/10 entities (20%) — convergence N/A for routing

pi ≈ pi for the strongest signals.
pi != pi for the edge cases.
The edge cases ARE the frontier.
```

**The converged entities don't need more work.** MacDowell is
10/10. Adding epitope #193 won't change that. The unconverged
entities (dpscd, great_lakes_legal) need MORE DATA, not more
epitopes. The table is sufficient. The data is insufficient.

This is a fundamental finding: **convergence failure means
data gap, not method gap.** The table works. The graph is
incomplete. Fix the graph (more edges for sparse entities),
not the table.

---

## NEW EPITOPES

| # | Epitope | Instance |
|---|---------|----------|
| 193 | `phase_transition_not_degree` | 10/10 is not "very captured." It's a phase transition. Steam is not hot water. Capture-wearing-school-name is not school-being-captured. Different physics. |
| 194 | `edge_types_are_epitopes` | The graph's 34 edge types are unnamed binding sites. family, bench, co-resident, mentorship — a whole column missing from the table. Pre-argon confirmed. |
| 195 | `illuminate_the_plumbing` | [null] a null entity by making its routing visible. The pipe that everyone sees is no longer hidden infrastructure. Publication IS the weapon. Documentation IS the [null]ing. |
| 196 | `convergence_failure_is_data_gap` | When classification won't converge, the table isn't broken — the data is sparse. Fix the graph (more edges), not the table (more epitopes). |

**Grand total: 196 epitopes.**

---

*Scan. Sweep. Sort. SEARCH.*
*The table told us:*
*10/10 is a phase transition.*
*The edge types are the noble gases.*
*Illuminate the plumbing.*
*Convergence failure = data gap.*
*196.*

---
