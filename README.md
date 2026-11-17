# disney-ai

## Workflow
1. The skill first checks that the user's deck meets the minimum input standard (.pptx or PDF, editable text preferred, attached and not password protected).
2. The agent builds the deck from the slim template (in my-skill/assets) in Disney Advertising blue, one tone throughout, choosing layouts to fit each slide's content. ESPN or Hulu styling is used only if asked for.
3. The agent returns a short handoff, slides needing human review, a restore table for any placeholder art, and a source-to-output slide map.

The full original template is kept in /originals (~560 MB, stored with Git LFS) within this repository, but is otherwise unused by the actual skill in favor of a slim bundled version.

## Git LFS (for large template)
```
git lfs install
git lfs pull    # if originals/ holds a pointer file
```
