Test Cases – PDF.js Search & Hyphenation

Scope

These test cases focus on verifying the behavior of PDF.js search when dealing with:

- Hyphenated words
- Words split across lines
- Soft hyphens
- Non‑hyphenated control cases

---

TC-1 – Search for non‑hyphenated word (control)

**Objective:**  
Verify that search works correctly for a simple, non‑hyphenated word.

**Steps (vibe-coded):**

- Open PDF.js demo viewer with a test PDF.
- Identify a word that appears clearly and is not hyphenated.
- Use Ctrl+F and search for that exact word.
- Navigate through all matches.

**Expected:**

- All occurrences of the word are found and highlighted.
- No missed matches.

---

TC-2 – Search for visually hyphenated word using unhyphenated query

**Objective:**  
Verify that searching for an unhyphenated word matches a visually hyphenated word in the document.

**Steps:**

- Open the PDF used in Issue #20689 (or similar).
- Locate a word displayed as `in-ference` (or similar hyphenation).
- In the search box, type `inference` (without hyphen).
- Execute the search.

**Expected:**

- The search should highlight the `in-ference` occurrence.
- The user should not need to guess the hyphenation pattern.

---

TC-3 – Search for visually hyphenated word using exact hyphenation

**Objective:**  
Verify behavior when the user includes the hyphen in the search query.

**Steps:**

- Using the same PDF, locate `in-ference`.
- In the search box, type `in-ference`.
- Execute the search.

**Expected:**

- The search should highlight the `in-ference` occurrence.
- If not, behavior should be documented as a limitation.

---

TC-4 – Soft hyphen handling

**Objective:**  
Verify how search behaves with soft hyphens (invisible hyphenation characters).

**Steps:**

- Use a PDF known to contain soft hyphens (or create one).
- Search for a word that includes a soft hyphen in the underlying text.
- Compare behavior with and without the soft hyphen in the query.

**Expected:**

- Soft hyphens should not break search matching.
- Searching for the plain word should still find the occurrence.

---

TC-5 – Cross‑browser search behavior

**Objective:**  
Verify that search behavior is consistent across browsers.

**Steps:**

- Repeat TC‑002 and TC‑003 in:
  - Firefox
  - Chrome
  - Edge
- Use the same PDF and search terms.

**Expected:**

- Search behavior should be consistent across browsers.
- Any differences should be documented.

---

TC-6 – Multiple occurrences of hyphenated word

**Objective:**  
Verify that all occurrences of a hyphenated word are found.

**Steps:**

- Use a PDF where the same hyphenated word appears multiple times.
- Search for the unhyphenated form.
- Navigate through all matches.

**Expected:**

- All occurrences are found and highlighted.
- No partial or missing matches.

