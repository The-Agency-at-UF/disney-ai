# disney-ai

## Workflow
1. The skill first checks the user's deck meets the minimum input standard (.pptx or PDF, editable text, attached and not password protected).
2. Choose between the default style, Hulu, or ESPN and the agent builds your deck from the slim template (inside /assets).
3. The agent returns a detailed description of the changes made and any issues it detects that are left for human review.

The full original template is kept in /originals (~560 MB, stored with Git LFS) for restoring images by hand.

## Git LFS (for large template)
```
git lfs install
git lfs pull    # if originals/ holds a pointer file
```
