# Portfolio — Milad Rivandi

A single-file static portfolio (`index.html`) that behaves like a running backend:
routes, API-style responses, a terminal (press `` ` ``), a Lab and hidden secrets.
No build step, no dependencies.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole site (HTML + CSS + JS) |
| `404.html` | Custom not-found page |
| `.nojekyll` | Tells GitHub Pages to skip Jekyll processing |
| `.gitignore` | Keeps `resume.pdf` out of the public repo (it contains a phone number) |

## Preview locally

Open `index.html` in a browser, or run a tiny server:

```bash
npx serve .
```

## Deploy to GitHub Pages

1. Create a **public** repo named `MiladRv.github.io` (user site) — or any name for a project site.
2. Push this folder:

```bash
git remote add origin https://github.com/MiladRv/MiladRv.github.io.git
git branch -M main
git push -u origin main
```

3. On GitHub: **Settings → Pages → Build and deployment → Source: Deploy from a branch → `main` / `(root)` → Save**.
4. The site goes live at `https://miladrv.github.io` within a minute or two.

## Connect a custom domain (later)

1. Buy the domain, then add DNS records at your registrar:
   - **Apex domain** (`example.dev`): four `A` records → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - **`www`**: a `CNAME` record → `miladrv.github.io`
   - Check GitHub's docs for the current IPs before relying on these.
2. Create a file named `CNAME` in this folder containing only your domain, e.g. `example.dev`, then commit and push. (Or set it in **Settings → Pages → Custom domain**.)
3. Wait for DNS to propagate, then tick **Enforce HTTPS** in **Settings → Pages**.

Don't create `CNAME` before you own the domain — it would break the default `github.io` URL.

## Resume file

`resume.pdf` is git-ignored on purpose: it contains a personal phone number and the repo is public.
To publish a resume, use a version without the phone number, then delete the `resume.pdf` line from `.gitignore`.
Until then the footer's `resume.pdf` link will 404 on the live site — remove or change that link in `index.html` if you don't publish it.

## Contact form

The form currently opens the visitor's email client (`mailto:`). For direct submissions on a static site,
point it at a form service such as Formspree or Web3Forms.
