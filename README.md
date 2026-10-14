# nexvion.lab FIXED - No 404

## Why you got 404?
You included CNAME = nexvion.lab before setting DNS. GitHub then redirects github.io -> nexvion.lab which doesn't exist yet = 404.

## FIX v2 (This ZIP)
- Removed CNAME by default
- Added 404.html (same as index.html) - GitHub Pages needs this
- Added .nojekyll
- index.html at ROOT

## Deploy steps that WON'T 404:

1. Create NEW repo on GitHub: `nexvion-lab` (public)
2. Unzip this file, upload ALL files to repo root (not in subfolder)
3. Commit
4. Settings -> Pages:
   - Source: Deploy from a branch
   - Branch: main / (root)
   - SAVE
5. Wait 1-2 mins, visit: https://YOURUSERNAME.github.io/nexvion-lab/
   - MUST work, no 404

6. ONLY AFTER that works, if you own nexvion.lab domain:
   - Add file CNAME with content `nexvion.lab` (or add via Settings -> Pages -> Custom domain)
   - DNS: Add 4 A records to 185.199.108.153, .109.153, .110.153, .111.153
   - CNAME www -> YOURUSERNAME.github.io

If still 404:
- Check repo is PUBLIC
- Check files are at root, not in /nexvion-lab-project/ subfolder
- Check Actions tab -> Pages build succeeded
- Hard refresh: Ctrl+Shift+R

