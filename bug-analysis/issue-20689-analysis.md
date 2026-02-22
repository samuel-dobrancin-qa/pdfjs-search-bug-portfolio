# Bug Analysis – PDF.js Issue #20689: Search fails on some hyphenated words

## 1. Summary

PDF.js’s built‑in search feature fails to find certain words that appear hyphenated or split across lines in the PDF content. For example, searching for a word like `inference` does not match the visually present text `in-ference` in the document.

This indicates a problem in how text is extracted, normalized, and indexed for search when hyphenation or line breaks are involved.

- **Upstream issue:** https://github.com/mozilla/pdf.js/issues/20689
- **Area:** Text extraction, search indexing, hyphenation handling
- **Severity (QA view):** High for usability and trust in search

---

## 2. Environment

- **Browser:** Mozilla Firefox 147.0.3  
- **OS:** Tahoe 26.2  
- **PDF.js build:** Demo viewer at https://mozilla.github.io/pdf.js/web/viewer.html (latest at time of testing)  
- **Test document:** Default TraceMonkey demo PDF (or the PDF referenced in the issue)

(You can adjust this section with exact URLs or commit hashes if you capture them.)

---

## 3. Steps to Reproduce

```text
1. Open the PDF.js demo viewer:
   https://mozilla.github.io/pdf.js/web/viewer.html

2. Load the TraceMonkey demo PDF (default) or the PDF attached/linked in Issue #20689.

3. Press Ctrl+F (or use the search toolbar).

4. In the search box, type a word that appears hyphenated in the document.
   Example: "inference" when the document shows "in-ference".

5. Press Enter / Next to search.

6. Observe whether the search highlights the expected occurrence.
