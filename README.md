# harness-share-html-deck

A small Pi skill for turning the current session into a navigable HTML presentation deck.

## What it does

When the user asks to present or summarize the current session as an HTML deck, the skill:

- asks whether the deck should be shareable
- if not shareable, creates a local standalone `.html` deck and returns its full file path
- if shareable, creates the deck locally, uploads it as a **secret gist** by default, and returns:
  - the GitHub gist link
  - an `htmlpreview.github.io` rendering link
  - a reminder: `Ask me to delete this when you're done using it`

## Notes

- The deck is expected to be a standalone HTML file with navigation.
- The skill keeps prompting minimal and lets the agent infer deck content from the current session when possible.
- GitHub secret gists are unlisted, not truly private.
