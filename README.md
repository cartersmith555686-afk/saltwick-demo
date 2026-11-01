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

## Set up the admin account (phone or computer)

The staff panel at `#admin` signs in as `saltwick-admin`. The page only stores a salted hash of your password.

1. Upload `index.html` to the repo first (see the steps above), then open the live site and go to `#admin`.
2. Type a password of 12 or more characters twice and tap **Make setup code**. Nothing is sent anywhere.
3. Tap **Copy setup code**.
4. In the repo, tap **Add file > Create new file**, name it `admin.json`, paste the code, and commit.
5. Go back to `#admin` and sign in with `saltwick-admin` and your password.

Keep `admin.json` in the same folder as `index.html`. Only the hash is in that file.

This is a convenience lock, not real account security. Anyone who copies the page or `admin.json` can try passwords offline, so use a long, unusual password. For real logins, the site needs a backend such as Supabase.
