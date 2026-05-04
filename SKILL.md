---
name: harness-share-html-deck
description: Create a navigable HTML deck that presents or summarizes the current session. Use when the user asks to present, summarize, or turn current-session work into an HTML deck, slides, or a shareable presentation.
---

When this skill matches, do the following:

1. Before creating the deck, ask a single question: whether the user wants it to be shareable.
2. If the user says yes:
   - Create the HTML deck locally first.
   - Prefer a secret gist (GitHub does not offer truly private gists; use secret/unlisted rather than public unless the user explicitly asks for public).
   - Use `gh gist create` to upload it as a gist.
   - Also produce an `htmlpreview.github.io` URL for the raw gist HTML file.
   - Return the GitHub gist link, the `htmlpreview.github.io` link, and the reminder: `Ask me to delete this when you're done using it`.
3. If the user says no:
   - Create the HTML deck locally.
   - Return only the full local file path so it is clickable.

Requirements:
- The deck should be a standalone `.html` file with navigation.
- Keep prompting minimal and figure out the deck content yourself from the current session whenever possible.
- Final output should be either:
  - the full local file path, or
  - for shareable output: the GitHub gist link, the `htmlpreview.github.io` link, and `Ask me to delete this when you're done using it`.
- When creating a gist, prefer secret/unlisted by default.
