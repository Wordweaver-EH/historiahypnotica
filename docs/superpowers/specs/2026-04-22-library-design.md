# Historia Hypnotica — Library Design

**Date:** 2026-04-22  
**Scope:** Primary source archive, 1775–1930  
**Format:** File-based git repository (no web frontend for now)

---

## 1. Repository Structure

```
historiahypnotica/
├── README.md           — project description, points to INDEX.md
├── INDEX.md            — full catalog table of all texts
├── CONTRIBUTING.md     — sourcing and translation guidelines
├── 1770s/
├── 1780s/
├── 1790s/
├── 1800s/
├── 1810s/
├── 1820s/
├── 1830s/
├── 1840s/
├── 1850s/
├── 1860s/
├── 1870s/
├── 1880s/
├── 1890s/
├── 1900s/
├── 1910s/
├── 1920s/
└── 1930s/
```

All decade folders created upfront. Each contains `.md` files for texts from that decade.

---

## 2. Filename Convention

```
YYYY_Author_ShortTitle.md
```

Examples:
- `1775_Gassner_PiousHealth.md`
- `1784_Mesmer_AnimalMagnetism.md`
- `1843_Braid_Neurypnology.md`

`ShortTitle` is 1–3 words, CamelCase, no spaces or special characters.

---

## 3. File Header Schema

Every file opens with rich YAML frontmatter, followed by the full text body:

```yaml
---
author: Johann Joseph Gassner
year: 1775
title: "How to Live Piously and Healthily, and Also to Die Peacefully and Devoutly"
language_original: German
source_url: https://www.deutsche-digitale-bibliothek.de/item/FOMMF3FBZS4GVZPBZ7VK7AQWKLJDM4FV
translation: "AI-assisted (Claude), 2024"
translator_notes: "Some terms like 'animal spirits' retained verbatim. Uncertain passages marked [?] inline."
subject_tags: [exorcism, faith-healing, devil, early-hypnosis-precursor]
related_works: [1784_Mesmer_AnimalMagnetism, 1784_Puységur_Memoirs]
---

# Title

[full text body]
```

**`translation` field values:**
- `original English`
- `published: Translator Name, YYYY`
- `AI-assisted (Claude), YYYY`
- `hybrid: published base, AI-assisted gaps, YYYY`

Uncertain passages in the body use `[?]` inline. Significant translation decisions go in `translator_notes`.

---

## 4. INDEX.md Catalog

`INDEX.md` at the repo root is the browsable catalog, maintained manually as texts are added:

```markdown
# Index

| Year | Author | Title | Language | Translation | Tags |
|------|--------|-------|----------|-------------|------|
| 1775 | Gassner | How to Live Piously and Healthily... | German | AI-assisted | exorcism, faith-healing |
| 1784 | Mesmer | Memoir on Animal Magnetism | French | Published (Bloch, 1980) | animal-magnetism |
```

Rows added in chronological order. Tags pulled from frontmatter `subject_tags`.

---

## 5. Sourcing Workflow

The library grows iteratively, one author cluster at a time:

1. **Deep research** — for each figure, research their writings, contemporaries, citations, and who cited them. Output: a curated list of works to acquire.
2. **Curate target list** — decide scope before hunting for sources.
3. **Manual source search** — find best available scan or transcription (Google Books, Internet Archive, Deutsche Digitale Bibliothek, Gallica/BnF, HathiTrust, Wellcome Collection).
4. **Acquire + translate** — use existing published English translation if one exists; otherwise AI-assisted with notes in frontmatter.

---

## 6. Translation Policy

Priority order:
1. **Published English translation** — check WorldCat and Google Scholar first
2. **Hybrid** — published base with AI-assisted gaps, noted in `translator_notes`
3. **AI-assisted (Claude)** — full translation, always disclosed in frontmatter

Uncertain passages marked `[?]` in body text. Translator always credited.

---

## 7. Scope Definition

Included:
- Animal magnetism / mesmerism (Mesmer era)
- Artificial somnambulism (Puységur onwards)
- Hypnosis theory and practice (Braid, Elliotson, Esdaile)
- Nancy School: suggestion and psychotherapy (Liébeault, Bernheim)
- Paris School: hysteria and hypnosis (Charcot, Janet)
- Early psychoanalysis where hypnosis is central (Breuer, early Freud)

Excluded:
- Pure psychiatry or neurology with no hypnosis connection
- Secondary sources and histories (primary sources only)
- Works after 1930
