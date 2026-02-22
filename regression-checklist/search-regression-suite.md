Regression Checklist – PDF.js Search & Text Extraction

This checklist is designed to prevent regressions bugs in PDF.js search behavior, especially around hyphenation and line‑split words.

---

1. Basic Search Functionality

- [ ] Search finds simple, non‑hyphenated words.
- [ ] Search highlights all occurrences of a word.
- [ ] Search navigation (Next/Previous) works correctly.
- [ ] Case sensitivity behaves as expected (if supported).

---

2. Hyphenated Words

- [ ] Search for unhyphenated query matches visually hyphenated words (e.g., `inference` → `in-ference`).
- [ ] Search for the exact hyphenated form (`in-ference`) behaves consistently.
- [ ] Hyphenated words at line breaks are handled correctly.
- [ ] Multiple occurrences of the same hyphenated word are all found.

---

3. Line‑Split Words

- [ ] Words split across lines without visible hyphens are tested (e.g., `inter` + `national`).
- [ ] Search for the full logical word (`international`) is evaluated.
- [ ] Behavior is documented if not supported.

---

4. Soft Hyphens & Special Characters

- [ ] PDFs containing soft hyphens are tested.
- [ ] Search ignores soft hyphens when matching words.
- [ ] Unicode normalization is considered (e.g., accented characters).

---

5. Cross‑Browser Behavior

- [ ] Search behavior verified in Firefox.
- [ ] Search behavior verified in Chrome.
- [ ] Search behavior verified in Edge.
- [ ] Any differences are documented.

---

6. Performance & Stability

- [ ] Search remains responsive on large PDFs.
- [ ] No crashes or freezes when searching repeatedly.
- [ ] No memory spikes observed during intensive search.

---

7. Regression Around Fixes

If a fix is implemented for Issue #20689:

- [ ] New automated tests cover hyphenated word search.
- [ ] Manual regression confirms:
  - Hyphenated words are found.
  - Non‑hyphenated words still work.
  - No new issues introduced in search.
- [ ] Edge cases (soft hyphens, line splits) are re‑tested.

