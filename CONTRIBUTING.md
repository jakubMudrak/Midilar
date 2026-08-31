# Editing this site

The site is two hand-authored files — `index.html` and `cable_editor.html` — served straight
from `main` by GitHub Pages. There is no build step: what is in the repo is what ships.

## Edit files in place. Never delete-and-re-upload.

When changing `index.html` through github.com, use the **pencil / Edit this file** button on the
existing file and commit the change.

Do **not** use *Add files via upload* to replace `index.html` with a copy from your computer, and
do not delete the file and upload a new one. Two things go wrong when you do:

1. **Git records it as a whole-file rewrite.** A two-line change shows up as roughly
   `-10,127 / +10,125`. `git bisect` and `git log -S` stop working, so when something breaks
   later there is no way to find out when or why.
2. **It silently discards other people's merged work.** This has already happened once: commit
   `19efa50` uploaded a local copy that predated a merged pull request, which reverted the whole
   cleanup in that PR — a duplicated 192 KB image came back, saved rack layouts started being
   wiped on every launch, and lazy-loading and the social/meta tags disappeared. None of it was
   intentional and none of it was visible in the diff.

If you have been editing a copy locally, either commit it with git, or paste your changes into
the github.com editor rather than uploading the file over the top of it.

## Prices

Prices live in `prices.json`. Edit that file directly — no HTML or JavaScript changes are needed
to change a price, add a module, or turn pricing on and off.
