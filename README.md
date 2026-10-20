# disney-ai

## NEW Workflow
1. The skill tries to fetch the full original template at /originals (~560 MB, stored with Git LFS) for full-quality images.
2. It checks the file is real (over 1 KB, not an LFS pointer, opens in python-pptx, 144 slides).
3. If the fetch or check fails, it falls back to the slim template (inside /assets) and tells the user backgrounds are reduced quality.
4. It transforms the user's deck on the chosen template. Every output needs human review.

## Setup for Git LFS
```
git lfs install
git lfs pull    # if originals/ holds a pointer file
```
