Automation Outline – PDF.js Search & Hyphenation

This is a high‑level, vibe‑coded automation design for validating search behavior in PDF.js, with a focus on hyphenated and line‑split words.

---

1. Goals

- Validate that the search feature can find:
  - Non‑hyphenated words
  - Visually hyphenated words
  - Line‑split words
- Ensure behavior is consistent across PDFs and browsers.
- Provide a foundation for automated regression tests once a fix is implemented.

---

2. High‑Level Automation Flow

``text
Test Suite: Search & Hyphenation

- For each test PDF in a predefined set:
  - Launch browser with PDF.js viewer.
  - Load the target PDF.
  - For each search scenario:
    - Input search term.
    - Trigger search.
    - Capture:
      - Whether a match is found.
      - Number of matches.
      - Position(s) of matches (if accessible).
    - Compare results with expected outcomes defined in metadata.
  - Log pass/fail per scenario.
