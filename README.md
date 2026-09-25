# 🎯 Bug Bounty Targets

Obscure + self-hosted + small SaaS bug bounty / VRP / CVD programs from many countries.
Low crowd, real payouts. Single static page — no build step.

## View locally
Just open `index.html`, or serve:
```bash
cd bug-bounty-targets
python3 -m http.server 8080
# → http://localhost:8080
```

## Add more programs (later)
Edit `programs.json` and append an object:
```json
{
  "name": "Example SaaS",
  "country": "Germany",
  "type": "self-hosted bounty",
  "url": "https://example.com/security",
  "scope": "*.example.com",
  "contact": "security@example.com",
  "rewards": "Low €100 / High €1000",
  "safe": "Responsible disclosure, no DoS",
  "notes": "SaaS, low crowd"
}
```
Refresh the page — filters + search update automatically.

## Push to GitHub + Pages
```bash
cd bug-bounty-targets
git init
git add .
git commit -m "bug bounty targets page"
gh repo create bug-bounty-targets --public --source=. --push
# then: repo Settings → Pages → Deploy from branch → main → / (root)
```
Or create the repo on github.com manually and:
```bash
git remote add origin git@github.com:<you>/bug-bounty-targets.git
git branch -M main
git push -u origin main
```

## Files
- `index.html` — the single page (search + filters + cards)
- `programs.json` — all programs data (edit me to grow the list)
- Old CSVs kept outside this folder: `/workspace/bug_bounty_*.csv`

> ⚠️ Always respect scope + safe harbor. Out-of-scope testing is illegal.
