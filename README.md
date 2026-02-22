# PDF.js Search Bug – Hyphenated Word Failure (Issue #20689)

This repository documents a real QA analysis of an open bug in Mozilla’s PDF.js project, where the built‑in search fails to find certain hyphenated words in a PDF document.

- **Upstream project:** [mozilla/pdf.js](https://github.com/mozilla/pdf.js)
- **Issue:** [#20689 – Search fails on some hyphenated words](https://github.com/mozilla/pdf.js/issues/20689)
- **Role:** Manual QA / Quality Engineer
- **Focus:** Search reliability, text extraction, hyphenation handling, regression strategy, and automation design.

## Contents

- `bug-analysis/issue-20689-analysis.md`  
  Detailed analysis of the bug, environment, reproduction steps, expected vs actual behavior, and impact.

- `test-cases/search-hyphenation-test-cases.md`  
  Structured test cases covering hyphenated words, line breaks, and related search scenarios.

- `regression-checklist/search-regression-suite.md`  
  A regression checklist to prevent future search regressions in PDF.js.

- `automation-outline/search-index-automation-outline.md`  
  A high‑level, vibe‑coded automation outline for validating search behavior and text extraction.

- `screenshots/`  
  Visual evidence of the issue and comparison with expected behavior.

## Tech & Context

- **Component under test:** PDF.js text extraction and search subsystem
- **User impact:** Users cannot reliably search for words that are hyphenated or split across lines, reducing trust in the viewer and making documents harder to navigate.

This project is part of my QA portfolio, demonstrating real‑world analysis of an open‑source issue, including test design, regression strategy, and automation thinking.
