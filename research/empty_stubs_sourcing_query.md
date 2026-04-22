# Research Query: Source All Empty Stubs

*Generated 2026-04-22. Run against Google Books, BSB, Gallica, Internet Archive, HathiTrust.*

---

## Goal

For each text below, find:
1. The best available digitized source (preferably full text, not snippet-only)
2. Whether a published English translation exists
3. Direct URL to the scan or transcription

---

## Texts to Source

### 1. Arthur Ashley Sykes — *An Enquiry into the Meaning of Demoniacks in the New Testament* (1737)
- **Language:** English (original)
- **Expected source:** Google Books, Internet Archive (18th-century English text, high digitization probability)
- **Search terms:** `"Sykes" "Demoniacks" "New Testament" 1737`, `"Arthur Ashley Sykes" enquiry demoniacks`
- **Notes:** English original — no translation needed. Likely on Google Books or Archive.org.

---

### 2. Ludovico Antonio Muratori — *De viribus imaginationis* (c. 1745)
- **Language:** Latin (possibly also Italian as *Della forza della fantasia umana*)
- **Expected source:** Google Books, BSB, Internet Archive
- **Search terms:** `"Muratori" "De viribus imaginationis"`, `"Muratori" "fantasia umana" 1745`, `Muratori imagination 1745`
- **Notes:** Verify exact publication year and title. Muratori (1672–1750) — Italian Catholic Enlightenment figure. The Italian edition *Della forza della fantasia umana* may be more accessible than the Latin.

---

### 3. Ferdinand Sterzinger — *Die aufgedeckten Gassnerischen Wunderkuren* (1774)
- **Language:** German
- **Expected source:** BSB, VD18, Deutsche Digitale Bibliothek
- **Search terms:** `"Sterzinger" "Gassner" 1774`, `"aufgedeckten Gassnerischen Wunderkuren"`, `Sterzinger Gassner Wunderkuren`
- **Notes:** Sterzinger was a Theatine friar and Enlightenment rationalist at the Munich Academy of Sciences. This is a key critical eyewitness account. VD18 is the best starting point.

---

### 4. Anton de Haen — *De Miraculis Liber* (1776)
- **Language:** Latin
- **Expected source:** Google Books, BSB, Internet Archive
- **Search terms:** `"de Haen" "De Miraculis" 1776`, `"Anton de Haen" miracles 1776`, `"De Haen" "De Miraculis Liber"`
- **Notes:** De Haen (1704–1776) was a Dutch imperial court physician in Vienna. Paradoxically concluded Gassner's cures were genuine but diabolical. Published posthumously or in his final year. Check for an 18th-century German or French summary alongside the Latin original.

---

### 5. Johann Joseph Gassner — *Antwort auf die Anmerkungen... Münchnerisches Intelligenzblat* [2nd edition] (1776)
- **Language:** German
- **Expected source:** BSB (we already have the 1st edition scan; 2nd edition may be the BSB scan `17768694428888bsb10622674.pdf` already in repo)
- **Search terms:** `"Gaßner" "Antwort" "Münchnerischen" 1776 "Zwote Auflage"`, VD18 `Gaßner Antwort 1776`
- **Notes:** May be identical to the 1775 first edition with minor corrections. Confirm whether the BSB PDF already in `1776_Gassner_ResponseMunich.pdf` is this second edition — if so, transcribe from that.

---

### 6. Franz Anton Mesmer — *Mémoire sur la découverte du magnétisme animal* (1779)
- **Language:** French
- **Expected source:** Gallica (BnF), Google Books, Internet Archive
- **Search terms:** `"Mesmer" "magnétisme animal" 1779`, `"Mémoire sur la découverte du magnétisme animal" Mesmer`, `Mesmer 1779 magnetism Didot`
- **Notes:** Published Paris/Geneva by Didot. A published English translation exists: *Mesmerism* trans. by V.R. Myers (Macdonald, London, 1948) and also in *Animal Magnetism* trans. George Bloch (1980). Check WorldCat for the Bloch translation availability.

---

### 7. James Braid — *Neurypnology, or the Rationale of Nervous Sleep* (1843)
- **Language:** English (original)
- **Expected source:** Internet Archive, Google Books (well-known text, very likely fully digitized)
- **Search terms:** `"Braid" "Neurypnology" 1843`, `"Neurypnology" "nervous sleep" Braid Churchill`
- **Notes:** Published London, John Churchill, 1843. Should be freely available on Archive.org. No translation needed.

---

### 8. James Braid — *Magic, Mesmerism, Hypnotism, etc., Historically and Physiologically Considered* (1844–1845)
- **Language:** English (original)
- **Expected source:** Internet Archive, Google Books, Wellcome Collection
- **Search terms:** `"Braid" "Magic Mesmerism Hypnotism" "Medical Times" 1844`, `Braid hypnotism "Medical Times" 1844 1845`
- **Notes:** Series of articles in *Medical Times*, Vol. XI, 1844–1845. May be harder to find as a standalone document — look for the journal volume rather than a standalone pamphlet.

---

### 9. James Braid — *The Power of the Mind over the Body* (1846)
- **Language:** English (original)
- **Expected source:** Internet Archive, Google Books, Wellcome Collection
- **Search terms:** `"Braid" "Power of the Mind over the Body" 1846`, `"Braid" "mind over body" Churchill 1846`
- **Notes:** Published London, John Churchill, 1846. Shorter pamphlet. Wellcome Collection holds significant Braid material.

---

### 10. Albert Moll — *Der Hypnotismus* (1890)
- **Language:** German (with an English translation)
- **Expected source:** Internet Archive, Google Books
- **Search terms:** `"Moll" "Hypnotismus" 1890`, `"Albert Moll" hypnotism 1890 Fischer`
- **Notes:** Published Berlin, Fischers Medizin, 1890. An English translation exists: *Hypnotism* trans. A.F. Hopkirk (Walter Scott, London, 1890). The English translation is almost certainly on Archive.org — check there first.

---

### 11. Pierre Janet — *Les Médications psychologiques* (1919)
- **Language:** French (with English translation)
- **Expected source:** Internet Archive, Google Books, Gallica
- **Search terms:** `"Janet" "Médications psychologiques" 1919`, `"Pierre Janet" "psychological healing" 1925`, `"Janet" "Felix Alcan" 1919 psychologie`
- **Notes:** 3-volume work, Paris, Felix Alcan, 1919. English translation: *Psychological Healing: A Historical and Clinical Study*, trans. Eden and Cedar Paul, Macmillan, New York, 1925. The English translation is very likely on Archive.org. Confirm whether to use the French original or the 1925 English translation.

---

## Output Format Requested

For each text, return:

```
Title: [short title]
Source URL: [direct link to best scan]
Translation available: yes/no — [details if yes]
Format: [full text / snippet only / partial]
Notes: [anything relevant]
```
