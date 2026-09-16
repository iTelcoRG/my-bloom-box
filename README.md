# My Bloom Box

Static Astro homepage and shared site shell, based on the supplied Shopify theme. No commerce backend or external services.

## Local review

Run `npm install`, then `npm run dev`. Open http://localhost:4321.
On Windows where PowerShell blocks npm.ps1, use `npm.cmd` instead of `npm`.

## Checks and deployment

Run `npm run check` and `npm run build`. Upload the **contents** of `dist/` to cPanel `public_html`. No Node runtime is needed on the server. `npm run preview` serves the built output locally.

## Editing

- Global colours, typography variables and responsive styles: `src/styles/global.css`.
- Navigation, announcement, copyright, draft product details and sample testimonials: `src/data/site.ts`.
- Homepage sections: `src/components/`; composition: `src/pages/index.astro`.
- Shared metadata and shell: `src/layouts/SiteLayout.astro`.
- Local SVG placeholder illustrations: `public/images/`. Replace with approved photos, update dimensions/alt text and remove placeholder captions in `PlaceholderImage.astro`.

The supplied ZIP contains no photography or final product data. Product contents, story expansion, announcement and testimonials are draft copy. Testimonials are visibly marked as illustrative, not actual reviews. Confirm these before publishing. Pricing is intentionally awaiting confirmation.

Bloomie, FAQ, Contact, Privacy, Terms and Cart have simple coming-soon destinations to keep shell navigation usable; they are not complete content pages. Supply approved contact details and policies before launch. Newsletter inputs are disabled and explicitly state that no data is collected. The cart is a placeholder only.

The Shopify baseline’s colours, Georgia/Arial fonts, split layouts, soft cards and dark footer are preserved. Pink buttons/announcement use dark text for legibility. No eyebrow headings, remote fonts, remote image services, analytics or ecommerce dependencies are included.
