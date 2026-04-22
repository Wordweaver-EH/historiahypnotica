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
