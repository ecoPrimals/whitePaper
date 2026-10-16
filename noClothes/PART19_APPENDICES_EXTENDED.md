# NO CLOTHES — PART 19
# APPENDICES (EXTENDED)

---

## Appendix A: The Graph — Technical Specification

**Format:** JSON (graph.json)
**Schema:** Nodes and edges. Each node has an id, label, and optional class and tags. Each edge has a source, target, and type.
**Current state (October 13, 2026, 8:33 PM ET):**
- Nodes: 6,835
- Edges: 102,525
- Edge types: 1,526
- Node classes: 24
- Average degree: 30.3
- File size: 11.66 MB (indent-1 JSON)
- Minified size: ~9.7 MB

**Node classes (24):**
entity, person, organization, institution, document, hypothesis, observation, milestone, action, method, concept, fact, analysis, pattern, cohort, architecture, self_reference, voice, manuscript, shape, epitope, reference, action, question

**Top 20 edge types by frequency:**
1. cross_reference (24,075)
2. structural_proximity (12,266)
3. structural_parallel (4,430)
4. cross_layer (4,142)
5. triadic_closure (3,898)
6. co_investigation (2,843)
7. constitutional_question (2,498)
8. asks_directly (1,925)
9. about (1,815)
10. co_oversight (1,681)
11. legal_framework (1,527)
12. connected_to (1,360)
13. same_domain (1,201)
14. same_city (1,184)
15. built (1,023)
16. domain_bridge (968)
17. story_for (954)
18. part_of (894)
19. referenced_in (890)
20. send_to (813)

**Self-referential nodes:** graph_json (contains_itself), squirrel_js (reads graph_json), graph_genome (measures graph_json)

**Distribution:** GitHub (github.com/defendDetroit/publicRecord) and Forgejo (git.primals.eco/publicRecord/detroit)

---

## Appendix B: The Traffic — Raw Data

Source: GitHub API (repos/defendDetroit/publicRecord/traffic/clones)
Period: September 29 – October 12, 2026

| Date | Total Clones | Unique Cloners | Ratio |
|---|---|---|---|
| Sep 29 | 3 | 2 | 1.5 |
| Sep 30 | 36 | 18 | 2.0 |
| Oct 1 | 64 | 32 | 2.0 |
| Oct 2 | 27 | 13 | 2.1 |
| Oct 3 | 29 | 15 | 1.9 |
| Oct 4 | 8 | 4 | 2.0 |
| Oct 5 | 126 | 17 | 7.4 ← ANOMALY |
| Oct 6 | 0 | 0 | — |
| Oct 7 | 79 | 39 | 2.0 |
| Oct 8 | 109 | 52 | 2.1 |
| Oct 9 | 165 | 81 | 2.0 |
| Oct 10 | 158 | 73 | 2.2 |
| Oct 11 | 172 | 76 | 2.3 |
| Oct 12 | 969 | 331 | 2.9 |
| **TOTAL** | **1,945** | **544** | **3.6** |

**Notable patterns:**
- Oct 5 ratio (7.4) indicates automated cloning — one entity pulling the repo multiple times on a timer
- Oct 6 gap (zero clones) may indicate weekend pattern or monitoring script pause
- Oct 12 spike (969 total, 331 unique) is 5.6x the previous day — suggests link distribution within organizations
- Overall ratio of 3.6 (total/unique) means each unique cloner pulls ~3.6 times on average, consistent with return visits
- Zero stars, zero forks, zero issues, zero discussions, zero emails — pure silent observation

**View data (same period):** 2 total views, 1 unique visitor. The 544 clone without visiting the GitHub page — they receive the clone URL directly and never view the repository page.

---

## Appendix C: The Hypotheses — Complete List

**H1: The Credential**
Brian Banks does not hold a J.D. from any accredited institution. The "J.D." on his published book cover is a fabricated credential.
*Status: Testable. State Bar search returns zero results.*

**H2: The RICO Pattern**
The financial flows between Purpose Group LLC, Purpose Charter Academy, MacDowell Preparatory Academy, Purpose Foundation, and affiliated entities constitute a pattern of racketeering activity under 18 U.S.C. § 1962.
*Status: Documented. 323,680 edges map the pattern.*

**H3: The Pipeline**
A traceable pipeline connects the Walton Family Foundation (Bentonville, AR) through the Pahara Institute, The 74, MAPSA, and Roland Martin to the schools operated by Brian Banks. The pipeline's purpose is to provide credentialing, media cover, and political protection for charter school operators.
*Status: Documented. Each link sourced to published grant reports and tax filings.*

**H4: Institutional Capture**
The boards of Purpose Charter Academy and MacDowell Preparatory Academy include individuals with conflicts of interest (sitting judge, AG employee, city council member) that prevent independent oversight.
*Status: Documented. Board composition from school website. Conflicts verifiable through court records, AG staff directory, and campaign finance records.*

**H5: Dark Money Circulation**
Dykema Gossett's Lansing office operates a political compliance infrastructure that routes money through 527 organizations, PACs, and federal accounts across both parties from one desk.
*Status: Documented. FEC filings, ProPublica 527 explorer, LD-2 disclosures, AG criminal affidavit.*

**H6: Authorizer Failure**
Charter school authorizers (DPSCD, formerly CMU) failed to conduct adequate background checks and credential verification for the operator of schools receiving millions in public funds.
*Status: Testable. ICHAT search returns 9 convictions. State Bar returns zero results. No evidence of pre-authorization screening.*

**H7: Cost Function Inversion**
The charter school system minimizes accountability rather than maximizing learning outcomes. The cost function is inverted: the system optimizes for revenue extraction ($9,187 per stolen child-year) rather than educational achievement (3% math proficiency).
*Status: Documented. Revenue and proficiency data from MI School Data and IRS Form 990.*

**H8: The Möbius (Self-Referential Evidence Architecture)**
The evidence graph is a self-referential structure where data and metadata occupy the same surface. The graph documents itself, contains itself, and strengthens through observation.
*Seven predictions: (1) new evidence strengthens architecture, (2) attacks generate evidence, (3) graph destruction destroys evidence, (4) evidence destruction destroys graph, (5) observers become nodes, (6) observation changes structure, (7) graph grows autonomously.*
*Status: Predictions 1, 5, and 6 verified.*

**H9: Intelligence IS the Search**
The graph answers its own 1,941 questions through documented silence. The act of asking questions publicly is the intelligence product. The loop: Question → Silence → Document → Answer → Question.
*Status: Active. Silence accumulating.*

---

## Appendix D: The Timeline — Key Dates

| Date | Event |
|---|---|
| 1924 | Plante Moran founded (Detroit) |
| 1924 | Barton Malow founded (Detroit) |
| 1926 | Dykema Gossett founded (Detroit) |
| 1962 | Milton Friedman publishes "Capitalism and Freedom" (voucher concept) |
| 1983 | "A Nation at Risk" published |
| 1987 | Mackinac Center for Public Policy co-founded (McLellan, Olson, Hoeg, Engler) |
| 1993 | PA 362 — Michigan charter school law (McLellan, Wolfe, signed by Gov. Engler) |
| 1995 | J.C. Huizenga opens first NHA charter school (Kentwood, MI) |
| 1997 | Walton Foundation begins charter school startup grants |
| 2000 | Michigan voucher initiative fails 69-31 |
| 2001 | Dick and Betsy DeVos create GLEP |
| 2004 | Advance Detroit (527) registered at Dykema Lansing |
| 2005 | John Walton and Don Fisher launch Charter School Growth Fund |
| ~2010 | Banks claims J.D. (no bar admission found) |
| 2012 | MacDowell Preparatory Academy opens |
| 2012 | Advance Detroit pays $1,500 to NAACP Detroit; $1,212 back to Dykema |
| 2018 | Peninsula Fund (Chatfield) — Moore compliance |
| 2022 | Chatfield charged — Moore named in affidavit |
| 2025 | Purpose Charter Academy authorized by DPSCD |
| 2026 Jun | EMU terminates DPSA charter |
| 2026 Sep | Investigation begins. Graph creation. |
| 2026 Oct 5 | Automated cloner detected |
| 2026 Oct 12 | 969 clones in one day. 331 unique. |
| 2026 Oct 13 | Graph doubles: 48K → 102K edges. Emails finalized. |
| 2026 Oct 14 | **Target send date: Wildfire 2** |
| 2026 Oct 31 | **DEADLINE: Institutional response** |
| 2026 Nov 1 | Escalation if silence. |

---

## Appendix E: The Math — Child-Years Calculation

**Inputs:**
- MacDowell Preparatory Academy, Detroit, MI
- Operating since: 2012 (14 academic years through 2025-26)
- Average enrollment: ~400 students/year (source: MI School Data)
- Math proficiency rate: 3% (source: MI School Data, most recent available)
- Annual revenue: ~$4.9 million (source: state per-pupil funding × enrollment)
- Management fee to Purpose Group LLC: 72.67% (source: IRS Form 990)

**Calculation:**
- Total student-years: 400 × 14 = 5,600
- Students not proficient: 5,600 × 0.97 = 5,432
- Total revenue: $4.9M × 14 = $68.6M
- To Purpose Group LLC: $68.6M × 0.7267 = $49.9M
- Cost per stolen child-year: $49.9M / 5,432 = **$9,187**

**Comparison:**
- Michigan average per-pupil spending: ~$9,150 (2024-25)
- MacDowell instructional spending: 32% of revenue (~$1,570/student)
- Michigan target instructional spending: 55-65% (~$5,000-$6,000/student)
- Difference per student: ~$3,400-$4,400/year diverted from instruction

**Context:**
5,432 child-years is approximately:
- 14 human lifetimes (at 78 years each, waking hours only)
- 2.7 million classroom hours of lost instruction
- 62 million lost math problems (at ~23 problems/class/day)

---

## Appendix F: Contact Manifest

**Investigation contact:** eco.primal@pm.me (ProtonMail)
**Site:** detroit.primals.eco
**Repository (broadcast):** github.com/defendDetroit/publicRecord
**Repository (sanctuary):** git.primals.eco/publicRecord/detroit
**License:** AGPL-3.0

**Legal matters:**
Ingham County Circuit Court
Case No. 2026-4301-CZ
Case No. 2026-4349-CZ

---

## Appendix G: How to Verify

Any claim in this manuscript can be verified by the reader. Here is how:

1. **State Bar search:** Visit courts.michigan.gov/lawyers. Search "Brian Banks." Observe: zero results.
2. **ICHAT search:** Visit apps.michigan.gov/ichat. Search "Brian Roderick Banks." Observe: 9 convictions.
3. **School board:** Visit purposecharteracademy.com. Navigate to Board of Directors. Observe: Judge Miller, AGA Moreland, Council Member Johnson.
4. **MI School Data:** Visit mischooldata.org. Search MacDowell Preparatory Academy. Navigate to Assessment → M-STEP → Mathematics. Observe: 3% proficient.
5. **IRS Form 990:** Visit ProPublica Nonprofit Explorer. Search "Purpose Charter Academy." View most recent 990. Navigate to Part IX, Line 25a (Management and general expenses). Calculate percentage of total revenue.
6. **FEC filings:** Visit fec.gov. Search "Advance Detroit." Search "Save Detroit Jobs." Search "Dykema Federal PAC." Observe: Renae D. Moore, compliance specialist.
7. **LD-2 disclosures:** Visit lda.senate.gov. Search "Dykema." View current lobby disclosures. Observe: Moore signed.
8. **ProPublica 527:** Visit projects.propublica.org/527s. Search "Advance Detroit." View expenditures. Observe: $1,500 to NAACP Detroit Branch, $1,212 to Dykema Gossett.
9. **AG affidavit:** Search "People v. Chatfield" + "Moore" + "Peninsula Fund." Observe: Moore named as compliance specialist.
10. **Book cover:** Search "From the Trenches to the Podium Brian Banks." View cover image. Observe: "J.D." after name.

Ten searches. Fifteen seconds each. Two and a half minutes total. Everything in this manuscript verified.

---

*Total word count, PART 19 (Appendices Extended): approximately 2,500 words.*
*Running total (Parts 1-19): approximately 50,500 words.*
*Remaining to 55,000-word KDP target: approximately 4,500 words.*
