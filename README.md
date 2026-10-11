# PhreakBoutique Docs

Source for **[docs.phreakboutique.com](https://docs.phreakboutique.com/)**, the setup guides that ship with every PhreakBoutique order (via the QR code on the "What the duck" note).

Built with [Zensical](https://zensical.org) (the successor to Material for MkDocs). Pages are plain Markdown in `docs/`.

## Editing

```bash
pip install zensical
zensical serve          # live preview at http://localhost:8000
```

- Add or edit pages in `docs/`, and add new pages to `nav` in `zensical.toml`.
- Brand colors are in `docs/stylesheets/extra.css`. Logos are in `docs/assets/`.
- Pushing to `main` publishes the site automatically (`.github/workflows/docs.yml`).

## One-time setup

1. Create the GitHub repo `PhreakBoutique/phreak-docs` and push this folder to it.
2. In the repo, go to **Settings → Pages → Build and deployment → Source** and choose **GitHub Actions**.
3. Under **Settings → Pages → Custom domain**, enter `docs.phreakboutique.com`. GitHub will ask you to verify the domain.
4. At your DNS provider, add a **CNAME** record: `docs` → `phreakboutique.github.io`.
5. Once the certificate is issued, tick **Enforce HTTPS**.

With an Actions-based deploy, the custom domain is set in repo settings, so no `CNAME` file is needed.

## Print assets

`print/docs-qr.svg` (vector, for printing) and `print/docs-qr.png` point to `https://docs.phreakboutique.com/`. Because the QR code points at the root of the site, you can reorganize pages freely without reprinting cards.
