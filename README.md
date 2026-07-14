# CATLOG static product catalog

This is a frontend-only catalog designed for Netlify. There is no cart, checkout, database, or server.

## Manage products in the browser (Decap CMS)

After deploying to Netlify, enable **Identity** in **Project configuration → Identity**, invite your own email address, then enable **Git Gateway** in the Identity services section. Visit `https://your-site.netlify.app/admin/`, accept the email invitation, and log in. If your deployment branch is not `main`, update `branch: main` in `admin/config.yml` to the correct branch first.

The CMS gives you a visual editor to add, edit, delete, reorder, and upload product images. Press **Publish** to commit the changes to Git; Netlify automatically redeploys the catalog. There is no server, database, or custom backend to maintain. Decap CMS uses your repository as its content store.

## Manage products in code (optional)

Open `data/products.json`. Set `whatsappNumber` to your WhatsApp number in international format. The site strips spaces and punctuation before building the WhatsApp link, so `+971 585008564` is fine. Each item in `products` becomes a product card, searchable catalog entry, and product-detail modal.

## Deploy

1. Create a new Git repository and push this project.
2. In Netlify, select **Add new site → Import an existing project**.
3. Choose the repository. Netlify detects `netlify.toml`; no build command is needed.
4. If you use the Netlify subdomain, `it-catlog.netlify.app`, the repo is already configured. If you switch to a custom domain later, update `robots.txt`, `sitemap.xml`, and the canonical/Open Graph URLs in `index.html`.

For a larger catalog, migrate the `products` array to one JSON file per category or connect Decap CMS to a Git provider; the UI can keep the same fields.
