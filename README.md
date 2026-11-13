# Tokyo Guide

One static file: `index.html`. No build step.

## Preview

```bash
cd ~/projects/tokyo-guide && python3 -m http.server 8000
```

Open http://localhost:8000 (phone on same Wi-Fi: http://<mac-ip>:8000).

## Publish on GitHub Pages (hosikiti)

```bash
cd ~/projects/tokyo-guide
git init -b main
git add .
git commit -m "Add Tokyo guide"
gh repo create hosikiti/tokyo-guide --public --source=. --push
gh api -X POST repos/hosikiti/tokyo-guide/pages -f 'source[branch]=main' -f 'source[path]=/'
```

Site URL after 1–2 minutes: https://hosikiti.github.io/tokyo-guide/

Update later: edit `index.html`, then `git commit -am "Update" && git push`.
