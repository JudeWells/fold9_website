# Fold9 holding page

A minimal black holding page for `https://fold9labs.com/`, with white,
left-aligned Geist Pixel text: Fold9, "molecule design.", and a direct email link
to `jude@fold9labs.com`. No dependencies, JavaScript, or build step are required.

Geist Pixel Square is hosted locally in `fonts/`, with its OFL license included.
Font source: [Vercel Geist](https://github.com/vercel/geist-font).

## Preview locally

From this folder, run:

```sh
python3 -m http.server 8000 --bind 127.0.0.1
```

Open <http://127.0.0.1:8000>. Press Ctrl+C to stop the server.

## Publish with GitHub Pages

1. Commit and push these files to the `main` branch of
   <https://github.com/JudeWells/fold9_website>.
2. Open the repository's **Settings → Pages**. Under **Build and deployment**,
   select **Deploy from a branch**, then **main** and **/ (root)**, and save.
3. Set **Custom domain** to `fold9labs.com` and save before changing DNS.
   The included `CNAME` file records this domain; `.nojekyll` serves the static
   files without Jekyll processing.
4. At the domain's DNS provider, set these records:

   | Type | Name | Value |
   | --- | --- | --- |
   | A | @ | 185.199.108.153 |
   | A | @ | 185.199.109.153 |
   | A | @ | 185.199.110.153 |
   | A | @ | 185.199.111.153 |
   | CNAME | www | judewells.github.io |

   Replace conflicting website records for `@` and `www`; preserve email and
   unrelated records. Remove conflicting `AAAA` records if present, or use
   GitHub's IPv6 addresses from the documentation below.
5. Once GitHub verifies DNS and provisions the certificate, enable **Enforce
   HTTPS** in Pages settings. DNS and certificate provisioning can take up to
   24 hours.

Subsequent pushes to `main` update the page automatically. The `www` address
redirects to `https://fold9labs.com/` once both DNS records are configured.

These local files do not enable GitHub Pages or change your domain's DNS by
themselves.

Reference: [GitHub Pages custom domain documentation](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site).

## Other static hosting

Upload `index.html` and the `fonts/` directory, connect `fold9labs.com` in the
hosting provider's settings, and apply that provider's DNS records. No build
command is needed.
