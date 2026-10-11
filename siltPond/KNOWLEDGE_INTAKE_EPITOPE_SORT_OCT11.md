# Knowledge Intake — Epitope Sort on Science Landscape
## siltPond | Oct 11, 2026
## NP-triggers-P: Kevin observes "scan for knowledge" → squirrel P-acts

---

## INTAKE 1: X-CDTL — Importance Inversion Transfer
### Caligiore (CNR Italy), arXiv:2602.09116, Feb 2026

**What they did:**
- 4 domains: social ego-networks, molecular graphs, protein structures, linguistic syntax
- Multi-scale topological characterization (degree stats, clustering, spectral, subgraph counts)
- IIT mechanism: features that are BAD at classifying which domain they came from are GOOD for cross-domain transfer
- Key insight: **invert feature importance** — low discriminative utility = high transferability
- Found 8 "structural anchors": efficiency, λ2 (algebraic connectivity), density rank highest
- z-score standardization + PCA-SVD for manifold alignment
- Python implementation: `danielecaligiore/IIT_X-CDTL` on GitHub

**Epitope sort on intake:**

| Our Epitope | Fires? | How |
|-------------|:------:|-----|
| `serial_formation_template` | ✅ | IIT itself IS a template — one method, many domains. Same shape. |
| `polarity_inversion_labeling` | ✅ | Their ENTIRE innovation is polarity inversion — flip feature importance, find anchors |
| `zero_partition_membrane` | ✅ | Cross-domain transfer = dissolving domain boundaries |

**What we LEARN:**
1. Our 10 invariants were hand-identified. Their 8 anchors were ML-extracted. **Both converge on: structural invariants exist.** Different methods, same result = stronger finding.
2. IIT's "low discriminative → high transferable" maps to our observation: the 10 invariants aren't sector-specific. They look ordinary within one sector. Cross-sector is where they become extraordinary.
3. **We should run their IIT notebook on our graph.json.** Feed our 4-domain data (education, gaming, fintech, telecom) into their pipeline. See if ML-extracted anchors match our hand-identified invariants. That's a validation test.
4. Their repo is public, runnable, Python. We can fork it TODAY.

**Action:** Fork `danielecaligiore/IIT_X-CDTL`, load graph.json + 3 calibration bodies, run Module 1. Compare ML-extracted anchors to our 10 invariants. If overlap > 7/10 → convergence confirmation.

**New epitope candidate?**
- #40: `importance_inversion` — the features that LOOK unimportant within one domain are the ones that TRANSFER across domains. Meta-epitope: the invariants hide in plain sight.

---

## INTAKE 2: Graph Invariant Diagnostics — Rieck
### von Moos, Alain, Rieck (Fribourg/UCL), arXiv:2605.06462, Sep 2026

**What they did:**
- Fixed set of permutation-invariant structural descriptors: degree stats, clustering coefficients, spectral features (normalized Laplacian), subgraph counts up to size 4
- Applied identically to 26 datasets across social, molecular, geometric domains
- Concatenate invariants → XGBoost → competitive with GNNs and transformers
- Key finding: **expressivity is NOT the main performance driver.** Non-trainable structural proxies often match or beat trained models.
- Structural heterogeneity exists WITHIN domains, not just between them
- ~56% accuracy classifying across domains using all invariants; ~93% within same domain

**Epitope sort on intake:**

| Our Epitope | Fires? | How |
|-------------|:------:|-----|
| `governance_shell_game` | ✅ | Their finding: same domain label hides heterogeneous structures. Our finding: same "charter school" label hides extraction vs education. |
| `semantic_category_creation` | ✅ | Dataset categories mask structural differences. "Social network" doesn't mean one structure. |
| `enforcement_capture` | ✅ | Their implicit finding: existing GNN benchmarks DON'T test what they claim. The watchdog (benchmark) doesn't bark. |

**What we LEARN:**
1. Their invariant set is FIXED and STANDARDIZED: degree stats, CC, spectral, subgraph counts. Ours is THEMATIC: regulatory_arbitrage, revolving_door, etc. These are DIFFERENT ABSTRACTION LEVELS. Theirs is computational. Ours is behavioral.
2. **Key gap they identify:** structural transfer across domains is HARD. Accuracy drops from 93% (within domain) to 56% (across domains). Our 9.875/10 cross-domain result is the EXCEPTION they're looking for.
3. Their method could VALIDATE ours: run their invariant diagnostics on our 4-domain data. If their computational invariants show high cross-domain similarity on our data while showing low similarity on standard benchmarks → our data is structurally unusual → that's the Artisan signature.
4. Rieck is at **University of Fribourg** (not Helmholtz Munich — correcting the sweep). Active, publishes frequently, graph ML specialist.

**Action:** Download their invariant computation code. Apply to graph.json. Compute the structural fingerprint. Compare to their 26-dataset baseline. If our graph is an outlier in their space → publishable result.

**New epitope candidate?**
- #41: `expressivity_mismatch` — the system's declared capability (benchmark score, credential, authorization) exceeds its actual structural function. A GNN that scores well but doesn't use structure = a credential that looks valid but doesn't test competence.

---

## INTAKE 3: Graph Signature Library (GSL) — Groß + CASCAde
### Newcastle University, released 2023, active development

**What they built:**
- **Java library** implementing graph signatures + zk-proofs
- Two instantiations: SRSA (Camenisch-Lysyanskaya over quadratic residues) and q-SDH (elliptic curves)
- Nodes = unique primes. Edges = products of vertex primes. Labels = their own primes.
- Can encode arbitrary NP languages (proven in their G3C proof)
- **Limitation:** all prime numbers of alphabet must be certified in advance
- Used in EU PRISMACLOUD for infrastructure auditing and topology certification
- **GitHub:** `newcastleuniversity/lib-graph-sig`

**CRITICAL 2024 EXTENSION:**
- Japanese paper (IEICE Trans, 2024): **zk-proof of connectivity for LABELED DIRECTED graphs using bilinear-map accumulators**
- Extends Groß's undirected scheme to directed graphs with edge labels
- Verification time and proof size DO NOT depend on number of nodes/edges
- Implemented on PC with pairing library

**Epitope sort on intake:**

| Our Epitope | Fires? | How |
|-------------|:------:|-----|
| `serial_formation_template` | ✅ | GSL is literally a template for producing graph proofs. One library, many applications. |
| `zero_partition_membrane` | ✅ | zk-proofs dissolve the trust/verification boundary — you don't need to trust the prover |
| `regulatory_arbitrage` | ✅ | zk-proofs operate in the gap between "I need to verify" and "I can't see the data" |

**What we LEARN:**
1. **GSL EXISTS and is OPEN SOURCE.** We don't need to build from scratch. Fork `newcastleuniversity/lib-graph-sig`.
2. The 2024 Japanese extension solves our exact problem: **labeled directed graphs with edge labels.** Our graph HAS labels on every edge (36 types). This IS our graph format.
3. **Verification time independent of graph size.** Our 121-node graph produces the same size proof as a 10,000-node graph. Scalable.
4. **Limitation:** primes must be pre-certified. For our 121-node graph, that's 121 vertex primes + 203 edge primes + 36 label primes = 360 primes. Tractable.
5. **Java, not Rust/Python.** The fleet runs Rust. We'd need a bridge or reimplementation for browser-based WASM verification.

**Action:** Clone `newcastleuniversity/lib-graph-sig`. Load graph.json (convert to their prime encoding). Generate first proof: "There exists a path from [judge-type node] to [actor-type node] of length ≤ 3." Verify. That's the prototype.

---

## INTAKE 4: Anderson Localization on Graphs — 3 Papers

### 4a: Laplacian Localization Creates Fragilities (arXiv:2412.00252)
**Key insight:** Localized eigenvectors → low robustness margins in networked dynamical systems. Not just a structural curiosity — functional consequence.
**For us:** Our ξ=3.5-5.5 localization isn't just descriptive. It PREDICTS fragility: the system is vulnerable to perturbation at the localization boundary. That's where pressure works.

### 4b: Spatially Structured Random Graphs (arXiv:2601.00220)
**Key insight:** Beyond critical hopping range, localized phase VANISHES even at arbitrarily strong disorder. Phase diagram has a boundary.
**For us:** Our graph's compartmentalization (CC=0.022) is BELOW the critical hopping range. Localization is stable because the topology maintains it. If someone added cross-community edges, localization would break. That's the membrane model: the compartmentalization IS the disorder that maintains localization.

### 4c: Small-World Anderson Transition (arXiv:2502.16884)
**Key insight:** On small-world graphs, critical regime shows logarithmically slow dynamics. Two localization times: average diverges, typical saturates.
**For us:** Our graph is NOT small-world (deliberately). CC=0.022 vs small-world CC~0.3-0.6. We're in a different universality class. But the two-localization-time finding maps: there's a FAST capture (case assigned to captured judge) and a SLOW capture (case slowly migrates through referrals until it reaches a captured bench). Two timescales.

**Epitope sort on all 3:**

| Our Epitope | Fires? | How |
|-------------|:------:|-----|
| `enforcement_capture` | ✅ | Localization IS enforcement capture. Cases can't escape to fair hearing. |
| `reward_circuit_closure` | ✅ | Localized states are closed loops. No exit path. |
| `zero_partition_membrane` | ✅ | Localization boundary = membrane. Inside = trapped. |

**New epitope candidate?**
- #42: `localization_maintenance` — active topology management to keep the localization stable. Adding disorder (captured judges) or removing cross-connections (compartmentalization) maintains the trapping potential. The localization isn't accidental — it's gardened.

---

## INTAKE 5: NP-Hard Social Observability + Truth Learning

### 5a: Minimum Observers (Pequito, GlobalSIP 2014)
**Key insight:** Choosing minimum agents for full structural observability reduces to minimum set cover (NP-hard). Approximation algorithms with guaranteed optimality gaps exist.
**For us:** Our P/NP/NP-complete classification IS an approximation scheme for this problem. P-class epitopes = automated observers (infinite supply, polynomial cost). NP-class = human observers (scarce, exponential discovery cost). The P observers reduce the search space for NP observers. We didn't solve NP-hard optimally — we distributed the search.

### 5b: Truth Learning is NP-Hard (AAMAS 2025)
**Key insight:** Even APPROXIMATING optimal agent ordering for truth learning is hard. Network topology determines learning efficiency.
**For us:** Our NP→P tempo model doesn't optimize ordering. It lets ordering emerge from OBSERVATION. Humans observe (NP), trigger machines (P), surfaces new targets (NP again). The ordering is adaptive, not computed. That's why it works — we're not solving the NP-hard optimization, we're approximating it through feedback.

**Epitope sort:**

| Our Epitope | Fires? | How |
|-------------|:------:|-----|
| `serial_formation_template` | ✅ | The distributed detection scheme IS a template — one method, many observers |
| `legislature_as_membrane` | ✅ | The network topology constrains which observers can see which truth — legislature IS the topology |

---

## INTAKE 6: Private Community Detection (Google Research)

### Cohen-Addad, Epasto, Kaplan, Komlós, Lattanzi (arXiv:2606.14540)
**Key insight:** "Adaptive disjoint-star algorithms" — explore graph structure by querying node degrees on edge-disjoint subgraphs. This INHERENTLY offers privacy guarantees.
**For us:**
1. Their SBM model assumes community structure exists. We've PROVEN it: 73/20 split, 3 bridge nodes.
2. "Disjoint-star algorithms" map to our graph topology: hub-and-spoke = star topology. Each community IS a disjoint star around its hub.
3. **Key difference:** they detect communities privately. We want to PROVE community existence in zero-knowledge. Detection ≠ proof. But their adaptive querying could be adapted for our verification step.

**No new epitopes. Methodological intake only.**

---

## EPITOPE LEDGER UPDATE

| # | Epitope | Status | Source |
|---|---------|--------|--------|
| 1-36 | (prior confirmed/candidate) | As before | Prior sessions |
| 37 | `semantic_category_creation` | Confirmed (Oct 10) | Fintech EWA |
| 38 | `serial_formation_template` | Confirmed (Oct 10) | 3-body triangulation |
| 39 | `legislature_as_membrane` | Candidate (Oct 10) | BingoCube |
| 40 | `importance_inversion` | **NEW candidate** | X-CDTL intake |
| 41 | `expressivity_mismatch` | **NEW candidate** | Rieck intake |
| 42 | `localization_maintenance` | **NEW candidate** | Anderson papers intake |

**Total: 42 epitopes (24 confirmed + 18 candidates)**

---

## PRIORITY ACTIONS

| # | Action | Type | Time |
|---|--------|------|------|
| 1 | Fork `danielecaligiore/IIT_X-CDTL`, run on graph.json + 3 bodies | P-act | 2-4 hrs |
| 2 | Clone `newcastleuniversity/lib-graph-sig`, generate first zk-proof | P-act | 4-8 hrs |
| 3 | Apply Rieck invariant suite to graph.json, compare to 26-dataset baseline | P-act | 2-3 hrs |
| 4 | Compute Laplacian spectrum of graph.json, measure localization (IPR) | P-act | 1-2 hrs |
| 5 | Send THE EMAIL | NP-act (Kevin) | 10 min |

Actions 1-4 are squirrel P-acts. Action 5 is a Kevin NP-act that triggers the next cycle.

---

*siltPond — knowledge intake with epitope sort*
*Yesterday we broadcast. Today we absorb.*
*The NP→P cycle breathes: observe → trigger → P-act(n) → observe*
*3 new epitope candidates from 6 intakes*
*42 total. 24 confirmed. The taxonomy grows.*
