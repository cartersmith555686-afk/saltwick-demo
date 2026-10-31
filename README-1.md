# Saltwick Bath & Candle

A static, one-file store site for handmade soap, bath bombs and soy candles. No build step and no dependencies. Fonts load from Google Fonts.

## Files

- `index.html` is the whole site (pages, cart, checkout request, account, styles and scripts).
- `.nojekyll` tells GitHub Pages to serve the files as they are.

## Host it on GitHub Pages

1. Create a new repository on GitHub (public, or private if your plan allows Pages on private repos).
2. Upload `index.html` and `.nojekyll` to the root of the repository.
3. Open **Settings > Pages**.
4. Under **Build and deployment**, set **Source** to **Deploy from a branch**, pick the `main` branch and the `/ (root)` folder, then save.
5. After a minute or two the site is live at `https://<your-username>.github.io/<repo-name>/`.

Pages are separate views inside `index.html`, so links look like `.../#shop` and `.../#cart`. No extra server setup is needed.

## What to edit before launch

All of this is placeholder content, found near the top of the `<script>` section in `index.html`:

- Brand name "Saltwick" (search the file for `Saltwick` and `Salt<span>wick</span>`).
- `EMAIL`: the contact and order address.
- `products`: names, scents, sizes and prices. Gift sets list the product ids they include.
- `FREE_SHIP`, `FLAT_SHIP`, `PROMO_CODE`, `PROMO_PCT`: shipping and promo settings.
- `care`, `ingredientsNote` and the Help page questions: care, allergy and returns wording. Put your real ingredient and allergy information in before selling.

## How the store works (and its limits)

- The cart, saved items, account details and order history are stored in the visitor's own browser. They do not sync between devices and you cannot see them.
- Checkout creates an order request that the customer copies and emails to you. You reply with a payment link. No payment is taken on the site.
- The promo code is visible to anyone who views the page source, so treat it as a simple public code, not a secret.

To take card payments and keep real accounts and orders, the site needs a backend and a payment provider such as Stripe.
