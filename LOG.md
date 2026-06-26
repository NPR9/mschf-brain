# Ingest Log

---

## [2026-04-24] ingest | 12 transcripts

**Source type:** Interview/talk transcripts (cleaned, timestamp-stripped)
**Location:** `raw/transcripts/_cleaned/`

| # | Filename |
|---|----------|
| 1 | `_16 Jan 2019 Internet Got Turned on Its Head When Gabe Whaley Walked in _cleaned.txt` |
| 2 | `_19 Mar 2024 BUSINESS OF HYPE_cleaned.txt` |
| 3 | `_24 Feb 2020 Hacking Culture_ Gabriel Whaley _cleaned.txt` |
| 4 | `15 Oct 2025 mschf gabe whaley on outlasting hype and playing the crowd_cleaned.txt` |
| 5 | `21 Apr 2025 An Evening with MSCHF_o terrific_cleaned.txt` |
| 6 | `30 MAY 2024 ART OF GOING VIRAL - MSCHF GABRIEL WHALEY_cleaned.txt` |
| 7 | `9 Oct 2024 making MSCHF_cleaned.txt` |
| 8 | `every mschf product yet 2025 _cleaned.txt` |
| 9 | `march 2025 Protecting Viral Products_ MSCHF's Brand Protection Strategy Explained_cleaned.txt` |
| 10 | `oct 2025 -Gabe Whaley on Why MSCHF Makes Virality an Art Form_cleaned.txt` |
| 11 | `oct 2025 Making MSCHF, an Art and Discipline with Gabe Whaley_cleaned.txt` |
| 12 | `oct 2025Gabe Whaley TED TALK_cleaned.txt` |

**Output:** `wiki/Principles/INDEX.md`, `wiki/Drops/INDEX.md`, `wiki/Brand-DNA/INDEX.md`, `wiki/Creative-Process/INDEX.md`, `wiki/Timeline/INDEX.md`, `wiki/INDEX.md`

---

## [2026-04-24] ingest | Made by MSCHF (Phaidon, 2024)

**Source type:** Physical book, scanned PDF — fully image-based (pdftotext returns nothing)
**Location:** `raw/books/Made by MSCHF.pdf`
**Pages:** 362
**Extraction method:** PyMuPDF (`fitz.Matrix(2,2)` → PNG per page) → visual read per page
**Output:** `raw/books/book-full-extract.md` (2,800+ lines)

**Book structure documented:**

| Section | Pages | Content |
|---------|-------|---------|
| Essays | 1–127 | 8 commissioned essays (Cattelan/Papini, Blake Gopnik, Amy Adler, Daniel Lopatin, Kevin Wiesner missile quote) |
| Absurd Systems | 128–215 | Key4All (#118), Severed Spots (#24), This Foot Does Not Exist (#12), MSCHF Wholesale (#41), Tax Heaven 3000 (#150), Global Supply Chain Telephone (#179) |
| Project Archive | 216–270 | Complete catalog Archive #001–#202. Book itself = Archive #202. |
| Absurd Objects | 271–362 | Jesus Shoes (#7), Satan Shoes (#65), ATM Leaderboard (#140), Spot's Rampage (#58), Microscopic Handbags (#157), Infinite Relic (#54), Big Red Boots (#147) |

**Archive corrections made during extraction:**

| Drop | Old # | Correct # | Source |
|------|-------|-----------|--------|
| AlexaGate | #120 (misread) | **#031** | Project Archive table p.220 |
| Infinite Relic | #044 (misread) | **#054** | Absurd Objects opener p.335 |
| Chair Simulator | #119 (misread) | **#069** (digital) + #130a/b (gallery editions) | Project Archive p.231 |
| Spot's Rampage (BD) | — | **#058** | Absurd Objects opener p.311 |
| Archive #120 | AlexaGate | **No More Tears, I'm Lovin' It** (Perrotin show, 2022) | Project Archive p.243 |
| Spots Rampage (Roblox) vs. Spot's Rampage (BD) | merged | **Two separate drops** — #048 and #058 | Confirmed by opener headers |

---

## [2026-04-24] lint | wiki health check

**Checks run:**
- Orphan pages (no inbound wikilinks)
- Principles referenced in drops but absent from INDEX
- Archive number conflicts
- Stub pages (<500 bytes)
- Naming inconsistencies across files

**Issues found and fixed:**

| Issue | Fix |
|-------|-----|
| 4 empty ghost files at wiki root (compile_wiki.py artifacts) | Deleted |
| 3 principles missing from INDEX: `Always Punch Something Never Punch Down`, `Make Objects With a Point of View`, `Nothing Is Sacred` | Added as Principles #23–#25 |
| `Virality ≠ Success` duplicate heading number | Renumbered to #26 |
| `Death Is Designed Not Suffered` missing comma — 6 files | Bulk fixed via sed |
| `One Sentence + Three Sentences` variant — 7 files | Standardized to `Three Sentence Rule` |
| `Distribution as Design` shorthand — 3 files | Standardized to `Distribution Is a Design Discipline` |
| `birkinstock.md` — 56-byte stub | Rebuilt with full entry |

**Final state:**

| Metric | Count |
|--------|-------|
| Principles in INDEX | 26 |
| Individual drop pages | 14 |
| Drops in Quick Reference table | 80+ |
| Archive # conflicts | 0 |
| Orphan pages | 0 |
| Naming inconsistencies | 0 |
| Ghost/empty files | 0 |

---
