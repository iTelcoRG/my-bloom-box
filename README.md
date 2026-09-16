# My Bloom Box

Static Astro homepage and shared site shell, based on the supplied Shopify theme. No commerce backend or external services.

## Local review

Run `npm install`, then `npm run dev`. Open the local server URL shown by Astro with `/my-bloom-box/` appended. The configured base applies to local development and preview too.
On Windows where PowerShell blocks npm.ps1, use `npm.cmd` instead of `npm`.

## Checks and deployment

Run `npm run check` and `npm run build`. `npm run preview` serves the built output locally under `/my-bloom-box/`.

### GitHub Pages preview

`astro.config.mjs` sets `site: 'https://itelcorg.github.io'`, `base: '/my-bloom-box'` and `output: 'static'`.
The expected public URL is https://itelcorg.github.io/my-bloom-box/.

In the repository's **Settings > Pages**, set **Source** to **GitHub Actions**. After review, commit and push to `main`; `.github/workflows/deploy.yml` will install dependencies, run checks, build/upload with `withastro/action@v6`, and deploy with `actions/deploy-pages@v5`. It uses `actions/checkout@v6`, Node 24, the required Pages permissions, and cancels superseded workflow runs. Manual runs are available through **Actions > Deploy to GitHub Pages > Run workflow** once the workflow is on the default branch. Repository Actions policies must allow the referenced actions.

### Future cPanel deployment

For a domain-root cPanel deployment, change `site` in `astro.config.mjs` to the actual production origin and change `base` to `'/'` (or remove `base`). Then run `npm run build` and upload the **contents** of `dist/` to `public_html`. Rebuild for that target: the GitHub Pages build contains `/my-bloom-box/` asset paths and should not be uploaded unchanged to the domain root.

No Node runtime is needed on cPanel. There are no hosting adapters or runtime services. `src/utils/paths.ts` uses Astro's `import.meta.env.BASE_URL` for internal page/public asset paths, so only the configuration needs to change between hosting targets. Same-page fragment links remain relative; Astro handles the imported CSS and bundled scripts automatically.

## Editing

- Global colours, typography variables and responsive styles: `src/styles/global.css`.
- Navigation, announcement, copyright, draft product details and sample testimonials: `src/data/site.ts`.
- Homepage sections: `src/components/`; composition: `src/pages/index.astro`.
- Shared metadata and shell: `src/layouts/SiteLayout.astro`.
- Local SVG placeholder illustrations: `public/images/`. Replace with approved photos, update dimensions/alt text and remove placeholder captions in `PlaceholderImage.astro`.

The supplied ZIP contains no photography or final product data. Product contents, story expansion, announcement and testimonials are draft copy. Testimonials are visibly marked as illustrative, not actual reviews. Confirm these before publishing. Pricing is intentionally awaiting confirmation.

Bloomie, FAQ, Contact, Privacy, Terms and Cart have simple coming-soon destinations to keep shell navigation usable; they are not complete content pages. Supply approved contact details and policies before launch. Newsletter inputs are disabled and explicitly state that no data is collected. The cart is a placeholder only.

The Shopify baseline’s colours, Georgia/Arial fonts, split layouts, soft cards and dark footer are preserved. Pink buttons/announcement use dark text for legibility. No eyebrow headings, remote fonts, remote image services, analytics or ecommerce dependencies are included.
