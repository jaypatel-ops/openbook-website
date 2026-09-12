# OpenBook website

Tiny static site for **https://openbookbusiness.com** — App Store / Plaid support, privacy, and terms pages.

Same pattern as [unfold-website](https://github.com/jaypatel-ops/unfold-website): **no build step**. Plain HTML + CSS.

## Pages

| Path | Purpose |
|------|---------|
| `/` | Simple landing |
| `/support/` | App Store **Support URL** |
| `/privacy/` | App Store / Plaid **Privacy Policy URL** |
| `/terms/` | In-app Terms of Service |

## Local preview

```bash
cd ~/Documents/Projects/openbook-website
npx --yes serve .
```

Open the URL it prints (usually `http://localhost:3000`).

## Deploy (recommended: Vercel + Namecheap DNS)

1. Create a GitHub repo (e.g. `openbook-website`) and push this folder.
2. Go to [vercel.com](https://vercel.com) → **Add New Project** → import the repo.
3. Framework preset: **Other** (static). Root directory: `.`
4. Deploy.
5. In Vercel → Project → **Settings → Domains**, add your Namecheap domain (apex + optional `www`).
6. In Namecheap → Domain List → **Manage** → **Advanced DNS**, add the records Vercel shows (usually an `A` record for `@` and a `CNAME` for `www`).

Cloudflare Pages or Netlify work the same way.

After DNS propagates, your Plaid / App Store URLs will be:

- Privacy: `https://openbookbusiness.com/privacy/`
- Support: `https://openbookbusiness.com/support/`
- Terms: `https://openbookbusiness.com/terms/`
- Marketing (optional): `https://openbookbusiness.com`

## Operator details

- Operator: Elevate Software LLC (Illinois)
- Product: OpenBook
- Support / privacy email: `team@openbookbusiness.com`

Update `/privacy/` when data practices change (new Plaid products, analytics, etc.).
