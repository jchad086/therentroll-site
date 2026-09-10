# therentroll.ca

Static marketing site for **The Rent Roll**, a free weekly newsletter for Ontario
landlords and property managers, powered by [EasyServe](https://easyserve.ca).

Live at <https://www.therentroll.ca/>.

## Structure

No build step, no dependencies. Plain HTML with CSS inlined per page.

```
index.html            Landing page (beehiiv signup embed, FAQ, JSON-LD)
privacy/index.html    Privacy policy   -> /privacy
terms/index.html      Terms of service -> /terms
404.html              Branded not-found page
brand/                Favicon and app icons
og-image.png          1200x630 social card
CNAME                 www.therentroll.ca
```

Routes are directories rather than `.html` files so the extensionless URLs the
pages link to resolve without relying on server rewrite behaviour.

## Hosting

GitHub Pages, served from `main` at the repository root. `www.therentroll.ca` is
canonical; the apex redirects to it.

DNS lives at GoDaddy: four `A` records on the apex pointing at the GitHub Pages
addresses, and `www` as a `CNAME` to `jchad086.github.io`. The `MX` and `TXT`
records belong to Google Workspace and Search Console. Leave them alone.

## Local preview

```bash
python3 -m http.server 8000
```

Serve from the repository root so the root-absolute paths resolve.

## Editorial

Newsletter drafting, the editorial brief and issue archives live in a separate
private repository. This one holds the public website only.

## Before the first send

- Add the business mailing address to `/privacy` and `/terms`. CASL requires it
  in every commercial message.
- Have a lawyer review both policy documents.
