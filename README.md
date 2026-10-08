# Randum Consulting

A lightweight, responsive, single-page consulting website with **no dependencies or build tools**. Designed for GitHub Pages.

## Preview locally

```bash
cd randum-consulting
python3 -m http.server 8000
```

Open http://localhost:8000 . Stop the server with Ctrl+C.

## Publish to GitHub Pages

1. Install GitHub CLI (`brew install gh`) and Git (`git --version`).
2. Authenticate in a browser: `gh auth login` (choose GitHub.com, HTTPS, and browser authentication).
3. From this folder, run:

   ```bash
   git init
   git add .
   git commit -m "Initial Randum Consulting website"
   git branch -M main
   gh repo create randum-consulting --public --source=. --remote=origin --push
   ```

4. On GitHub, open the repository **Settings → Pages**. Select **Deploy from a branch**, `main`, `/(root)`, then Save.
5. Under **Custom domain**, enter `www.randumconsulting.work.gd` and Save. This project's `CNAME` file already includes the same hostname.
6. In DNSExit, create a **CNAME record** with host `www` and target `<YOUR_GITHUB_USERNAME>.github.io` (without angle brackets, replace username). DNSExit appends `.randumconsulting.work.gd` to the host automatically. If there is already a `www` A/CNAME, replace it only after confirming it is no longer needed.
7. After DNS and HTTPS certificate issuance, check **Enforce HTTPS** in the GitHub Pages settings.

**Important:** Leave your existing ImprovMX MX and SPF TXT records untouched. They are independent of website hosting.

**Root/apex domain:** This initial deployment uses **www.randumconsulting.work.gd** because a CNAME is straightforward. To use the bare domain as well, configure a redirect or GitHub Pages apex A records separately after confirming how DNSExit handles them. Do not repurpose the existing apex A record blindly.

## Edit

- `index.html`: page text, services, contact email.
- `styles.css`: fonts, layout and colors.
- `favicon.svg`: icon.
- `CNAME`: GitHub Pages custom hostname.

The contact link uses `ngarg@randumconsulting.work.gd`. Be sure this alias exists and forwards correctly in ImprovMX.
