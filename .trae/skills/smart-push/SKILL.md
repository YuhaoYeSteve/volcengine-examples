---
name: "smart-push"
description: "Updates README.md with changelog/version info before pushing to GitHub. Invoke when user asks to push code, release version, or sync to remote."
---

# Smart Push with README Update

This skill augments the standard git push workflow by ensuring documentation is kept in sync with code changes.

## Workflow

When the user requests to push code or release a version:

1.  **Analyze Recent Changes**:
    *   Check `git log` for recent commits that haven't been pushed.
    *   Check staged/unstaged changes.
2.  **Draft Changelog**:
    *   Summarize the changes (features, fixes, refactors).
    *   Determine the new version number if applicable (or just use the date).
3.  **Update README.md**:
    *   Read `README.md`.
    *   Insert the changelog/updates in a dedicated "Recent Updates" or "Changelog" section.
    *   Ensure the format matches the existing file style.
4.  **Commit Documentation**:
    *   `git add README.md`
    *   `git commit -m "docs: update README with latest changes"`
5.  **Push**:
    *   Execute `git push`.

## Usage
*   Trigger this skill when the user says "push the code", "upload to github", or "release new version".
