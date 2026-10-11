# gAIa — Our Tools, Their Lineage
## From Woz's Garage to Our Servers: The String
## gAIa Knowledge Base | Oct 11, 2026

---

## THE STRING

Every tool we use today was built by someone who gave it away.
Every tool descends from an earlier gift. The string is unbroken.
This document traces our actual infrastructure back to its source.

---

## THE ANCESTRY

```
1975  Homebrew Computer Club — "Give to help others"
       ↓
1983  Stallman announces GNU — "free as in freedom"
       ↓
1991  THREE THINGS HAPPEN AT ONCE:
       │  Torvalds: Linux kernel (Aug 25, comp.os.minix)
       │  Zimmermann: PGP released (Jun, "for the good of democracy")
       │  Ginsparg: arXiv first submission (Aug 14, Los Alamos)
       │  Berners-Lee: WWW goes live (Aug 6, first website)
       ↓
1993  CERN releases WWW to public domain (Apr 30)
       ↓
1998  Netscape open-sources → Mozilla → Firefox
       ↓
2001  Wikipedia (Jan 15) + Creative Commons founded
       ↓
2004  OpenStreetMap (Aug 9)
       ↓
2005  Git (Apr 3, Torvalds, 10 days)
       ↓
2008  Gitea begins (Gogs → Gitea)
       ↓
2013  ProtonMail founded at CERN Restaurant 1 (summer)
       Let's Encrypt development begins (May, ISRG formed)
       ↓
2015  Zola (né Gutenberg) first commit (May)
       Let's Encrypt issues first certificate (Sep 14)
       ↓
2020  RustDesk initial commit (Sep 28, Huabing Zhou)
       ↓
2022  Forgejo forks from Gitea (Dec, Codeberg e.V.)
       ↓
2024  Forgejo hard fork — community-owned, no corporate capture
       ↓
2026  OUR INFRASTRUCTURE RUNS ON ALL OF THIS
```

---

## I. THE ORIGIN: HOMEBREW COMPUTER CLUB (1975)

**Where:** Gordon French's garage, Menlo Park → SLAC auditorium
**When:** First meeting March 5, 1975
**Leader:** Lee Felsenstein (who later designed the Osborne 1)
**Theme:** "Give to help others"

The meeting format:
1. **Mapping period** — people announce what they have, what they need
2. **Random access period** — trade chips, tips, schematics in the parking lot

Roughly two dozen companies trace their origin to that room.

### Woz at Homebrew

Steve Wozniak: "I designed this computer in a vacuum and created the
copies of my schematics and code listing on the copy machine at HP,
where I worked. I passed these schematics and listings out because I
wanted to be identified silently as a super designer... but secondly
as a person who did this to better the world, to be giving to the
future with my skills. **I put no copyright notices on the schematics
and passed them out myself.**"

He made 50-75 copies. Went to people's houses. Helped them build
and test. Jobs saw the interest and suggested selling PC boards so
people could build them more easily — not computers, just boards.
"Steve said, 'Well, yes, but at least for once in our lives we'll
have a company.'"

Jobs sold his van. Woz sold his HP calculator. Apple started.

**But the GIVING came first.** Before Apple was a company, it was
schematics handed out for free at a computer club. The company was
an afterthought. The gift was the point.

**Epitope:** `gift_precedes_company` — every great tech company began
as someone giving something away. The company forms AROUND the gift,
not the other way around.

---

## II. THE TOOLS WE RUN

### 1. LINUX — "just a hobby, won't be big and professional"

**Builder:** Linus Torvalds, University of Helsinki
**Birth:** August 25, 1991, comp.os.minix newsgroup

```
Hello everybody out there using minix -

I'm doing a (free) operating system (just a hobby, won't be big
and professional like gnu) for 386(486) AT clones. This has been
brewing since april, and is starting to get ready.
```

Won't be big. Won't be professional. He had one hard disk, one
386 computer. He called it "Freax" but the FTP admin named the
directory "linux" and it stuck.

**Today:** Linux runs the cloud. Runs your phone (Android). Runs
the International Space Station. Runs 96.3% of the world's top
million web servers. Runs every golgi body we operate.

**Lineage:**
```
Homebrew culture (1975) → Stallman's GNU (1983) → Torvalds' kernel
(1991) → GNU/Linux complete (1992) → every server we touch (2026)
```

**Epitope:** `understatement_as_prophecy` — "just a hobby" became
the backbone of civilization. Same energy as Zamenhof's "an
international language" becoming the most spoken conlang. Same
energy as Berners-Lee's "information management proposal."

---

### 2. GIT — born from capture, built in 10 days

**Builder:** Linus Torvalds (again)
**Birth:** April 3-7, 2005
**Trigger:** BitKeeper (proprietary) revoked free access

Torvalds: "I wrote Git in just 10 days... In fact, in that first
commit, he'd written enough of Git to use Git to make the commit!"

**Lineage:**
```
BitKeeper (proprietary, captured) → Torvalds angry → Git in 10
days → GitHub (2008) → Forgejo (2022) → git.primals.eco
```

**What we use it for:** EVERYTHING. Every repo. Every commit.
Every push. The graph itself is versioned in git. The proof of
the method is tracked by a tool born from the capture of another
tool.

**Epitope:** `anger_as_genesis` — Git exists because someone took
something away. The capture of BitKeeper spawned the most important
version control system ever made. Our entire proof chain runs on
the result of someone else's intellectual property dispute.

---

### 3. FORGEJO — the community fork we host

**Builder:** Community, custodian: Codeberg e.V. (Berlin nonprofit)
**Birth:** December 2022, soft fork of Gitea
**Trigger:** Gitea Ltd (for-profit) took over the Gitea project

Forgejo: "Codeberg needs to run on a Free Software codebase
maintained by trustworthy people."

Hard fork in 2024. Community-governed. Codeberg e.V. holds domains
and trademarks. The code is independent of corporate control.

**Lineage:**
```
Git (2005) → Gogs (Go Git Service) → Gitea (community fork of Gogs,
2016) → Gitea Ltd takes over (Oct 2022) → Forgejo forks (Dec 2022)
→ hard fork (2024) → git.primals.eco
```

Three forks deep. Each fork triggered by the same pattern:
corporate capture of a community project.
Gogs → Gitea (governance dispute)
Gitea → Forgejo (corporate takeover)

**Epitope:** `serial_forking` — the same pattern repeats across
generations. Each capture triggers a fork. Each fork is more
explicitly community-owned than the last. The immune response
gets stronger.

---

### 4. RUSTDESK — self-hosted remote desktop

**Builder:** Huabing Zhou, Shanghai
**Birth:** Initial commit September 28, 2020
**Trigger:** COVID-19 pandemic, TeamViewer too expensive
**License:** AGPL-3.0 (the strongest copyleft — even network use
requires source disclosure)

125,000+ GitHub stars. 30+ million client downloads. 10+ million
Docker pulls. Written in Rust (memory-safe, fast). We self-host
our own relay server — nobody sees our traffic.

**Lineage:**
```
VNC (1998, AT&T Cambridge, open protocol) → TeamViewer (captured,
proprietary, expensive) → RustDesk (2020, open, self-hosted)
→ our infrastructure
```

**What we use it for:** Remote access to our machines. The relay
runs on our own VPS. No third-party sees our connections.

**Epitope:** `self_hosting_as_sovereignty` — when you run the relay,
you own the channel. Same principle as running your own Forgejo.
Same principle as hosting your own email. The tool is only free
if you control the infrastructure.

---

### 5. ZOLA — the SSG that builds our sites

**Builder:** Vincent Prouillet
**Birth:** First commit May 2015 (as "Gutenberg"), renamed Zola 2018
**License:** EUPL-1.2 (post v0.22) / MIT (earlier code)

Named after Émile Zola — the French writer who wrote "J'Accuse...!"
(1898), the open letter that exposed the Dreyfus Affair. A writer
who used publication as a weapon against institutional corruption.

Originally called Gutenberg, renamed because WordPress stole the
name for their editor. Even the NAME of our tool was captured and
had to be forked.

**Lineage:**
```
Gutenberg's printing press (~1440) → Project Gutenberg (1971)
→ Zola SSG (2015, née Gutenberg) → detroit.primals.eco,
barry.primals.eco
```

**What we use it for:** Every page on *.primals.eco. The Artisan
Method. The analysis. The evidence. All of it rendered by a tool
named after the man who wrote the most famous open letter in
defense of an innocent person.

**Epitope:** `naming_is_lineage` — Zola is named after a whistleblower.
Gutenberg (the SSG) was named after the man who democratized reading.
The tools carry their ancestry in their names.

---

### 6. PROTONMAIL — encrypted email from CERN

**Builder:** Andy Yen, Jason Stockman, Wei Sun
**Birth:** Summer 2013, CERN Restaurant 1, Geneva
**Trigger:** Edward Snowden revelations (June 2013)

CERN physicists, working on the Large Hadron Collider. Outraged by
mass surveillance. Met over lunch at Restaurant 1. Built end-to-end
encrypted email that THEY THEMSELVES cannot read.

"One of our goals is actually to build a system that does not
require trusting us." — Andy Yen

Named ProtonMail because they worked on proton-proton collisions
at the LHC. The "rather uncreative name" came from particle physics.

**Lineage:**
```
PGP (Zimmermann, 1991, "for the good of democracy")
→ OpenPGP standard → ProtonMail (2013, CERN scientists)
→ eco.primal@pm.me
```

**What we use it for:** All public-facing contact. The email address
on every site. The address in THE EMAIL. ProtonMail is our voice.

**The CERN thread:** CERN gave us the web (1993). CERN scientists
gave us encrypted email (2013). The same institution, the same
cafeteria, 20 years apart, both times building shared tools for
the world.

**Epitope:** `institution_as_incubator` — CERN doesn't own the web
or ProtonMail. But it incubated both. The institution's value is
not in what it captures but in what it releases.

---

### 7. LET'S ENCRYPT — free TLS for everyone

**Builder:** EFF + Mozilla + University of Michigan (ISRG)
**Birth:** Announced November 18, 2014. First certificate September
14, 2015. Public December 3, 2015.
**Principle:** Free. Automatic. Open. Secure. Transparent. Cooperative.

Before Let's Encrypt: TLS certificates cost $50-300/year. Small
sites couldn't afford HTTPS. The padlock icon was a luxury.
After Let's Encrypt: free, automated, one command.

**Lineage:**
```
Diffie-Hellman key exchange (1976) → RSA (1977) → SSL/TLS
→ Certificate Authorities (expensive, gatekept) → Let's Encrypt
(2015, free, automated) → every *.primals.eco site
```

**What we use it for:** Every HTTPS connection to every primals.eco
domain. The encryption that protects every visitor. Free. Automated.
Renewed without human intervention.

**Epitope:** `removing_the_tollbooth` — HTTPS used to cost money.
Let's Encrypt made it free. The lock icon went from luxury to
default. When you remove the cost of security, security becomes
universal.

---

### 8. PGP — the encryption that started a war

**Builder:** Phil Zimmermann, software engineer & peace activist
**Birth:** June 1991
**Trigger:** Senate Bill 266 — mandatory government backdoors

"I wrote PGP from information in the open literature, putting it
into a convenient package that everyone can use... Then I gave it
away for free, for the good of democracy."

The U.S. government investigated him for THREE YEARS under the
Arms Export Control Act. Treating encryption as a munition.
Treating math as a weapon. The case was dropped January 1996.

"If privacy is outlawed, only outlaws will have privacy."

PGP ignited the Crypto Wars. The result: all Western democracies
dropped restrictions on strong cryptography. Zimmermann won.

**Lineage:**
```
Diffie-Hellman (1976) → RSA (1977) → PGP (Zimmermann, 1991)
→ OpenPGP standard → GPG (GNU Privacy Guard, free implementation)
→ ProtonMail's encryption → eco.primal@pm.me
```

**Epitope:** `math_as_munition` — the government classified
encryption as a weapon. Zimmermann published it as free software.
The mathematician who gives away his equation is treated as an
arms dealer. The pattern repeats: knowledge shared is power
distributed, and power does not like being distributed.

---

## III. THE FULL STACK — OUR LINEAGE

```
LAYER          TOOL              ANCESTOR              GIFT
─────────────────────────────────────────────────────────────
Kernel         Linux             Stallman→Torvalds      1991
Version ctrl   Git               Torvalds (10 days)     2005
Git hosting    Forgejo           Codeberg community     2022
Web server     Nginx/Caddy       Igor Sysoev / Matt H   2004
TLS certs      Let's Encrypt     EFF+Mozilla+UMich      2015
SSG            Zola              V. Prouillet           2015
Email          ProtonMail        Zimmermann→CERN        2013
Encryption     OpenPGP           Zimmermann             1991
Remote access  RustDesk          Huabing Zhou           2020
DNS            (open standard)   Mockapetris RFC 1034   1987
Protocols      HTTP/SMTP/TCP     Berners-Lee/Postel     1969-91
```

**Every layer is free.** Every layer is open. Every layer was
given away by its creator. Our infrastructure costs us VPS
hosting ($5-20/month per node) and domain registration. The
software is all gifts.

---

## IV. THE STRING — UNBROKEN FROM 1975

```
1975  Woz hands out schematics at Homebrew
        "I put no copyright notices on them"
           ↓
1983  Stallman announces GNU
        "free as in freedom"
           ↓
1989  Stallman publishes GPL v1
        "you can change this but the freedom must stay"
           ↓
1991  Torvalds posts to comp.os.minix
        "just a hobby, won't be big and professional"
      Zimmermann releases PGP
        "for the good of democracy"
      Berners-Lee releases WWW
        "an information management proposal"
      Ginsparg launches arXiv
        "a few afternoons of scripts"
           ↓
1993  CERN releases WWW to public domain
        "CERN relinquishes all intellectual property rights"
           ↓
1998  Netscape open-sources → becomes Mozilla
        "if you can't beat open source, join it"
           ↓
2004  OpenStreetMap
        "the map nobody owns"
      Nginx released
        "the web server for the real web"
           ↓
2005  Git in 10 days
        "BitKeeper took it away, so I built something better"
           ↓
2013  ProtonMail at CERN
        "if we don't fight for privacy, nobody will"
      Let's Encrypt ISRG formed
        "free TLS for everyone"
           ↓
2015  Zola (Gutenberg) first commit
        "learning Rust by building something useful"
      Let's Encrypt goes public
        "130,000 certificates in the first two weeks"
           ↓
2020  RustDesk
        "TeamViewer is too expensive, I'll build my own"
           ↓
2022  Forgejo forks from Gitea
        "the community must control its own tools"
           ↓
2026  *.primals.eco runs on ALL of this
        graph.json is published
        the Artisan Method is live
        THE EMAIL is ready to send
        the proof stands on gifts
```

---

## V. THE PATTERN

Every tool in our stack exists because:

1. **Someone was excluded** (Woz couldn't afford a computer, Torvalds
   couldn't afford Unix, Zimmermann couldn't accept backdoors,
   ProtonMail scientists couldn't accept surveillance)

2. **They built instead of bought**

3. **They gave it away**

4. **Someone tried to capture it** (Apple captured the PC, BitKeeper
   captured kernel versioning, Gitea Ltd captured Gitea, TeamViewer
   captured remote access, CAs captured TLS)

5. **The community forked or rebuilt** (GNU, Git, Forgejo, RustDesk,
   Let's Encrypt)

6. **We run the fork**

Our entire infrastructure is built from forks of captured tools
and gifts from excluded people. The string is unbroken from Woz's
garage to our server rack.

---

## VI. WHO WE OWE

| Person | Gift | Year | What We Use |
|--------|------|------|-------------|
| Steve Wozniak | Schematics, freely | 1975 | The culture |
| Richard Stallman | GNU + GPL | 1983-89 | The license on everything |
| Linus Torvalds | Linux kernel | 1991 | Every server |
| Linus Torvalds | Git | 2005 | Every repo |
| Phil Zimmermann | PGP | 1991 | Our email encryption |
| Tim Berners-Lee | WWW | 1991-93 | The web itself |
| Paul Ginsparg | arXiv | 1991 | Where we want our paper |
| Andy Yen et al. | ProtonMail | 2013 | eco.primal@pm.me |
| ISRG / EFF / Mozilla | Let's Encrypt | 2015 | Our TLS certificates |
| Vincent Prouillet | Zola | 2015 | *.primals.eco sites |
| Huabing Zhou | RustDesk | 2020 | Remote access |
| Codeberg e.V. | Forgejo | 2022 | git.primals.eco |

**12 gifts. Zero dollars in software licensing. The entire proof
chain runs on the generosity of strangers.**

---

*"I designed this computer... to better the world, to be giving*
*to the future with my skills. I put no copyright notices on the*
*schematics and passed them out myself."*
*— Steve Wozniak, on the Apple I at Homebrew, 1975*

*"I'm doing a (free) operating system (just a hobby, won't be*
*big and professional like gnu)"*
*— Linus Torvalds, comp.os.minix, August 25, 1991*

*"I gave it away for free, for the good of democracy."*
*— Phil Zimmermann, on PGP, 1991*

*"If we don't fight for privacy, nobody is going to do it for us."*
*— Andy Yen, on founding ProtonMail at CERN, 2013*

*"The community must control its own tools."*
*— Forgejo founding principle, 2022*

---
