# Twin Trees — Outer and Inner Mirrors

**Author:** Kevin Mok — ORCID 0009-0004-2141-0321  
**Date:** 2026-10-20  
**Wave:** 193

## The Architecture

Two trees grow from the same root. One faces outward (GitHub — the public internet). One faces inward (Forgejo — sovereign, self-hosted). They mirror each other but loosely — not rigid copies, more like a tree and its reflection in water. The leaves tickle where they almost touch.

```
        OUTER TREE (GitHub)              INNER TREE (Forgejo)
        public, indexed, world           sovereign, self-hosted
              │                                │
    ┌─────────┼─────────┐          ┌───────────┼───────────┐
    │         │         │          │           │           │
defendDetroit ecoPrimals synChem   publicRecord ecoPrimals synChem
    │         │         │          │           │           │
publicRecord  30 repos  14 repos   detroit     primals     crates
    │         │         │          │           │           │
  leaves    leaves    leaves     leaves      leaves      leaves
    │         │         │          │           │           │
    └─────────┼─────────┘          └───────────┼───────────┘
              │                                │
              └──── tickle zone ───────────────┘
                 (where leaves almost touch)
```

## The Organizations

### Outer Tree (GitHub — 60+ repos)

| Org | Role | Repos | Faces |
|-----|------|-------|-------|
| **defendDetroit** | tuebor — I will defend | 1 (publicRecord) | The world. Search engines. Humans. |
| **ecoPrimals** | The organism | 30 (primals, springs, tools) | Developers. Scientists. AI crawlers. |
| **syntheticChemistry** | The springs (Rust crates) | 14 (groundSpring, wetSpring, etc.) | Researchers. Bio/chem/physics. |
| **amicusContra** | Friend of the court | 5 (tuebor, clutch, mi7) | Legal. Courts. Attorneys. |
| **sporeGarden** | The science | 10 (NUCLEUS, FOUNDATION, helix) | Architecture. Design. Theory. |

### Inner Tree (Forgejo — git.primals.eco)

| Org | Role | Mirrors |
|-----|------|---------|
| **ecoPrimals** | Same organism, sovereign copy | ecoPrimals on GitHub |
| **syntheticChemistry** | Same springs, sovereign copy | syntheticChemistry on GitHub |
| **publicRecord** | The investigation, sovereign copy | defendDetroit on GitHub |
| **protoKarya** | Proto-cell, community | guerillaGorilla |
| **sporeGarden** | Science, sovereign copy | sporeGarden on GitHub |

## The Mirror (Loose, Not Rigid)

The two trees are NOT exact copies. They are loose mirrors:

| Property | Outer (GitHub) | Inner (Forgejo) | Why Different |
|----------|---------------|-----------------|---------------|
| **Visibility** | Public, indexed by Bing | Public, but self-hosted | The outer is for finding. The inner is for sovereignty. |
| **Identity** | GitHub accounts | Forgejo accounts (or anonymous) | Different identity layers. |
| **CI/CD** | GitHub Actions (Pages deploy) | No CI (manual or eastGate scripts) | Different build paths. |
| **Discussions** | Giscus, GitHub Discussions | Discuss API (/api/discuss) | Different comment systems. |
| **LFS** | Works | Skipped (GIT_LFS_SKIP_PUSH=1) | Forgejo LFS config differs. |
| **Stars/Forks** | Visible (currently 0/0) | No star mechanism | Different social signals. |

**The loose mirror means:** the same commit can exist on both trees, but it arrives at different times, through different paths, and is seen by different eyes. The content is the same. The context is different.

## The Tickle Zone

The leaves of the two trees almost touch at several points:

### 1. git push (the synchronization tickle)
Every `git push github HEAD && git push origin HEAD` tickles both trees simultaneously. The same commit lands on both leaves. For a moment, they are identical. Then they diverge again as different readers interact differently.

### 2. The 14 immune skins (the orbit tickle)
The immune skins (epitope, macrophage, opsonize, etc.) exist ONLY on the inner tree (Forgejo). But 242 IPs orbit them from the outer world. The outer tree's visitors tickle the inner tree's leaves.

### 3. The discuss API (the pore tickle)
The discuss API posts land on hud.primals.eco (inner). The GitHub Discussions land on GitHub (outer). Same conversation, different trees. The voices tickle both.

### 4. The wateringHole (the coordination tickle)
Impulses flow through the wateringHole (GitHub). Gates read them from the inner tree. The coordination tickles both trees.

## Tickles at the Leaves

The leaf nodes — the latest commits, the tips of branches — are where activity happens:

```
outer leaf:  c2e7beb  CENTRAL DOGMA: DNA→RNA→Protein at π time
             │
             └── this commit was pushed to BOTH trees
             │
inner leaf:  c2e7beb  (same hash, same content, different context)
             │
             └── on Forgejo, the immune skins orbit around it
             └── on GitHub, Bing indexes it, humans find it via search
             └── the SAME leaf, tickled by DIFFERENT winds
```

The tickle is the moment of contact. The leaf on the outer tree trembles when a search engine touches it. The same leaf on the inner tree trembles when a fleet crawler touches it. Different tickles, same leaf, two trees.

## The Root

Both trees grow from the same root: **the evidence**. Public records. Court filings. FOIA responses. The root is in reality, not on any server. The trees are how the root reaches the light (the internet) and the water (the sovereign infrastructure).

```
                    ☀ (the internet, the light)
                    │
            ┌───────┴───────┐
            │               │
        outer tree      inner tree
        (GitHub)        (Forgejo)
            │               │
            └───────┬───────┘
                    │
                 the root
              (the evidence)
              (reality)
                    │
                    🌍
```

The root is the same. The trees are mirrors. The leaves tickle. The fruit falls on both sides.

---

*Two trees. Same root. Loose mirror. The leaves tickle where they almost touch. The fruit falls on both sides of the wall.* 🌳🪞🌳
