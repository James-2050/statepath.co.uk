# Statepath public website source

## Purpose
This is the durable source path for the minimum live Statepath website.

It exists outside the task folder so the live site source does not depend on an active-task path that may later archive away.

## Files
- `index.html`
- `styles.css`
- `CNAME`
- `assets/`

## Recommended publish route
Use a **dedicated public GitHub repo + GitHub Pages**, and keep the current DNS authority where it is for now.

## Important current truth
- The current `council-office` repo is **private**.
- Direct GitHub inspection showed Pages is blocked here unless the repo is made public or upgraded.
- That means this repo is the **durable source owner**, not the direct live Pages host.

## Recommended live route
1. Create a dedicated public repo, ideally `statepath.co.uk`.
2. Copy the website files from this folder to the **root** of that public repo:
   - `index.html`
   - `styles.css`
   - `CNAME`
   - `assets/`
3. Enable **GitHub Pages** on that public repo.
4. Keep the current registrar/DNS authority in place.
5. Change only the website-facing DNS records.

## DNS settings for 123 Reg
### Apex/root
Add A records for `@` pointing to:
- `185.199.108.153`
- `185.199.109.153`
- `185.199.110.153`
- `185.199.111.153`

### www
Add a CNAME record:
- `www` -> `James-2050.github.io`

### Leave these alone
- current MX records
- current TXT records (including SPF / Google verification)
- current nameserver authority

## GitHub Pages note
The repo includes `.github/workflows/deploy-statepath-website.yml`.

That workflow remains useful as internal deployment prep/history, but it is **not** the current recommended live-host route because this repo is private.

For the actual public website repo, the simplest route is to place the site files at repo root and enable Pages there.

## Trustfulness note
These files are deployment-ready.

They are **not** proof that the website is already live.

Live status must be verified separately after:
- the public repo exists
- GitHub Pages is enabled there
- DNS web records are switched