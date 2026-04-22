# Historia Hypnotica — Library Scaffold Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Scaffold the full repository structure and migrate the existing Gassner text to the new standardized format.

**Architecture:** Flat decade-folder layout (1770s–1930s) with `.md` files using YAML frontmatter, a manual `INDEX.md` catalog, a `README.md` project description, and `CONTRIBUTING.md` workflow guidelines.

**Tech Stack:** Git, Markdown, YAML frontmatter. No build tools, no scripts — pure file-based archive.

---

## File Map

| Action | Path | Responsibility |
|--------|------|----------------|
| Create | `1770s/1775_Gassner_PiousHealth.md` | Migrated Gassner text with frontmatter |
| Delete | `Gassner1775` | Replaced by above |
| Create | `1780s/.gitkeep` … `1930s/.gitkeep` | Reserve all decade folders |
| Create | `README.md` | Project description, points to INDEX.md |
| Create | `INDEX.md` | Master catalog table |
| Create | `CONTRIBUTING.md` | Sourcing + translation workflow guide |

---

## Task 1: Create decade folders

**Files:**
- Create: `1780s/.gitkeep`, `1790s/.gitkeep`, `1800s/.gitkeep`, `1810s/.gitkeep`, `1820s/.gitkeep`, `1830s/.gitkeep`, `1840s/.gitkeep`, `1850s/.gitkeep`, `1860s/.gitkeep`, `1870s/.gitkeep`, `1880s/.gitkeep`, `1890s/.gitkeep`, `1900s/.gitkeep`, `1910s/.gitkeep`, `1920s/.gitkeep`, `1930s/.gitkeep`

Note: `1770s/` does not need `.gitkeep` — it will have the Gassner file.

- [ ] **Step 1: Create all empty decade folders**

```bash
mkdir -p 1780s 1790s 1800s 1810s 1820s 1830s 1840s 1850s 1860s 1870s 1880s 1890s 1900s 1910s 1920s 1930s 1770s
touch 1780s/.gitkeep 1790s/.gitkeep 1800s/.gitkeep 1810s/.gitkeep 1820s/.gitkeep 1830s/.gitkeep 1840s/.gitkeep 1850s/.gitkeep 1860s/.gitkeep 1870s/.gitkeep 1880s/.gitkeep 1890s/.gitkeep 1900s/.gitkeep 1910s/.gitkeep 1920s/.gitkeep 1930s/.gitkeep
```

- [ ] **Step 2: Verify**

```bash
ls -d */
```

Expected: 17 decade folders visible.

- [ ] **Step 3: Commit**

```bash
git add 1770s 1780s 1790s 1800s 1810s 1820s 1830s 1840s 1850s 1860s 1870s 1880s 1890s 1900s 1910s 1920s 1930s
git commit -m "scaffold: create decade folders 1770s–1930s"
```

---

## Task 2: Create CONTRIBUTING.md

**Files:**
- Create: `CONTRIBUTING.md`

- [ ] **Step 1: Create the file**

Full content of `CONTRIBUTING.md`:

```markdown
# Contributing to Historia Hypnotica

## Workflow for Adding a Text

Adding texts is a four-step research-first process. Do not hunt for sources before knowing exactly what you are looking for.

### 1. Deep Research
For each author or era, research thoroughly:
- What did they write? (titles, dates, languages)
- Who did they cite?
- Who cited them?
- What is the historical consensus on their significance to hypnosis history?

Output: a prioritized list of works to acquire, with full bibliographic details.

### 2. Curate Target List
Before searching for a source, decide:
- Is this work in scope? (see scope definition below)
- Is an English translation already available?
- Note the decision in a brief research log (can be a comment in a commit message or a notes file)

### 3. Find a Source
Search manually in this order:
1. Google Books (year-by-year search for era-appropriate terms)
2. Internet Archive / HathiTrust
3. Deutsche Digitale Bibliothek (German sources)
4. Gallica / BnF (French sources)
5. Wellcome Collection (medical/psychiatric history)
6. WorldCat / Google Scholar (verify published English translations)

Record the best source URL in the `source_url` frontmatter field.

### 4. Acquire and Translate
- If a published English translation exists: use it, credit the translator in `translation`
- If no translation exists: use AI-assisted translation (Claude), note it in `translation` and `translator_notes`
- Mark uncertain passages inline with `[?]`

---

## File Naming

```
YYYY_Author_ShortTitle.md
```

- `YYYY`: 4-digit year of original publication
- `Author`: surname only, no accents (Puységur → Puysegur), CamelCase if compound
- `ShortTitle`: 1–3 words, CamelCase, no spaces or special characters

Examples:
- `1775_Gassner_PiousHealth.md`
- `1784_Mesmer_AnimalMagnetism.md`
- `1843_Braid_Neurypnology.md`

Place the file in the correct decade folder (e.g., `1840s/` for 1843).

---

## Frontmatter Schema

Every file must open with this YAML block:

```yaml
---
author: Full Name
year: YYYY
title: "Full original title in English"
language_original: German | French | English | Latin | Other
source_url: https://...
translation: "original English" | "published: Translator Name, YYYY" | "AI-assisted (Claude), YYYY" | "hybrid: published base, AI gaps, YYYY"
translator_notes: "Any significant translation decisions, retained terms, or caveats. Leave blank if none."
subject_tags: [tag1, tag2, tag3]
related_works: [YYYY_Author_ShortTitle, ...]
---
```

### Subject Tags (use existing tags where possible)

| Tag | Use for |
|-----|---------|
| `animal-magnetism` | Mesmerian fluid theory |
| `somnambulism` | Artificial/magnetic sleep states |
| `hypnotism` | Braid and post-Braid terminology |
| `suggestion` | Nancy school, verbal suggestion |
| `hysteria` | Paris school, Charcot-era work |
| `exorcism` | Pre-mesmerist religious healing |
| `faith-healing` | Religious/spiritual healing framing |
| `early-hypnosis-precursor` | Pre-1780 works relevant by influence |
| `psychotherapy` | Early talk/suggestion therapy |
| `dissociation` | Janet, multiple personality, automatism |
| `case-studies` | Clinical/observational records |

---

## Scope Definition

**Included:**
- Animal magnetism and mesmerism (Mesmer era, 1775–1800)
- Artificial somnambulism (Puységur onwards)
- Hypnosis theory and practice (Braid, Elliotson, Esdaile, 1840s+)
- Nancy School: suggestion and psychotherapy (Liébeault, Bernheim)
- Paris School: hysteria and hypnosis (Charcot, Janet)
- Early psychoanalysis where hypnosis is central (Breuer, early Freud)
- Precursors with direct influence on the above (e.g., Gassner)

**Excluded:**
- Secondary sources and histories (primary sources only)
- Pure psychiatry or neurology with no hypnosis connection
- Works published after 1930

---

## Updating INDEX.md

After adding a file, add one row to the table in `INDEX.md`:

```markdown
| YYYY | Author | Short title | Language | Translation type | tag1, tag2 |
```

Keep rows in chronological order by year.
```

- [ ] **Step 2: Verify file exists**

```bash
cat CONTRIBUTING.md | head -5
```

Expected: `# Contributing to Historia Hypnotica`

- [ ] **Step 3: Commit**

```bash
git add CONTRIBUTING.md
git commit -m "docs: add CONTRIBUTING.md with sourcing and translation guidelines"
```

---

## Task 3: Create README.md

**Files:**
- Create: `README.md`

- [ ] **Step 1: Create the file**

Full content of `README.md`:

```markdown
# Historia Hypnotica

A chronological archive of primary sources on the history of hypnosis, 1775–1930.

Texts are organized by decade. Each document is an original work (or close translation of one) by a key figure in the development of hypnosis, animal magnetism, suggestion therapy, or related fields.

## Browse

See [INDEX.md](INDEX.md) for the full catalog.

## Contribute

See [CONTRIBUTING.md](CONTRIBUTING.md) for the workflow on adding new texts.

## License

MIT — see [LICENSE](LICENSE).
```

- [ ] **Step 2: Verify**

```bash
cat README.md | head -3
```

Expected: `# Historia Hypnotica`

- [ ] **Step 3: Commit**

```bash
git add README.md
git commit -m "docs: add README.md"
```

---

## Task 4: Create INDEX.md

**Files:**
- Create: `INDEX.md`

- [ ] **Step 1: Create the file**

Full content of `INDEX.md`:

```markdown
# Index

| Year | Author | Title | Language | Translation | Tags |
|------|--------|-------|----------|-------------|------|
| 1775 | Gassner | How to Live Piously and Healthily, and Also to Die Peacefully and Devoutly | German | AI-assisted (Claude), 2024 | exorcism, faith-healing, early-hypnosis-precursor |
```

- [ ] **Step 2: Verify**

```bash
cat INDEX.md
```

Expected: table with header row and one Gassner entry.

- [ ] **Step 3: Commit**

```bash
git add INDEX.md
git commit -m "docs: add INDEX.md catalog"
```

---

## Task 5: Migrate Gassner1775 to new format

**Files:**
- Create: `1770s/1775_Gassner_PiousHealth.md`
- Delete: `Gassner1775`

- [ ] **Step 1: Create `1770s/1775_Gassner_PiousHealth.md`**

The file opens with this YAML frontmatter, followed immediately by the full body text (copy verbatim from `Gassner1775`, starting at line 8 — omit lines 1–6 which were the old informal header):

```yaml
---
author: Johann Joseph Gassner
year: 1775
title: "How to Live Piously and Healthily, and Also to Die Peacefully and Devoutly"
language_original: German
source_url: https://www.deutsche-digitale-bibliothek.de/item/FOMMF3FBZS4GVZPBZ7VK7AQWKLJDM4FV
translation: "AI-assisted (Claude), 2024"
translator_notes: "Provenance note: copy bought by Philippus Jacobus of the Monastery of St. Peter in the Black Forest in 1779; later acquired by Zophius Meggle (Volume VI). Some terms such as 'animal spirits' and Latin citations retained verbatim. Uncertain passages marked [?] inline."
subject_tags: [exorcism, faith-healing, devil, spiritual-combat, suggestion, early-hypnosis-precursor]
related_works: []
---
```

Then, starting on the next line, paste the full text body from line 8 of `Gassner1775` to end of file.

- [ ] **Step 2: Verify frontmatter parses correctly**

Open `1770s/1775_Gassner_PiousHealth.md` and confirm:
- YAML block is between `---` delimiters
- All 9 frontmatter fields present
- Body text begins immediately after closing `---`
- File is not empty after the frontmatter

- [ ] **Step 3: Delete old file**

```bash
git rm Gassner1775
```

- [ ] **Step 4: Stage and commit**

```bash
git add 1770s/1775_Gassner_PiousHealth.md
git commit -m "migrate: Gassner1775 → 1770s/1775_Gassner_PiousHealth.md with frontmatter"
```

---

## Task 6: Push to remote

- [ ] **Step 1: Verify all changes look correct**

```bash
git log --oneline -6
git status
```

Expected: clean working tree, 5–6 commits since clone.

- [ ] **Step 2: Push**

```bash
git push origin main
```

Expected: remote updated, no errors.

---

## Self-Review Notes

- Spec section 1 (structure) → Tasks 1, 3, 4
- Spec section 2 (filename) → Task 5
- Spec section 3 (header schema) → Task 5 + CONTRIBUTING.md schema table
- Spec section 4 (INDEX.md) → Task 4
- Spec section 5 (sourcing workflow) → CONTRIBUTING.md
- Spec section 6 (translation policy) → CONTRIBUTING.md
- Spec section 7 (scope) → CONTRIBUTING.md

All spec sections covered. No placeholders. No TBD. File paths are exact.
