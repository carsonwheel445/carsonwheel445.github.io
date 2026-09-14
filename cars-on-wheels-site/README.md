# Cars on Wheels — website

## What's in here
- `index.html` — the whole site (one file: markup + booking form + JS)
- `dist/styles.css` — the compiled, production Tailwind CSS (generated, don't hand-edit)
- `src/input.css`, `tailwind.config.js`, `postcss.config.js` — the build setup that produces `dist/styles.css`

## Updating the "Satisfied Customers" number
In `index.html`, search for `id="customer-count"`. You'll see:

```html
<span class="text-4xl font-bold text-primary" id="customer-count">0</span>
```

Change the `0` to whatever the new count is, save, commit, and push. That's the whole update.

## Deploying with GitHub Pages
1. Create a new GitHub repo (e.g. `cars-on-wheels`) and push everything in this folder to it.
2. In the repo, go to **Settings → Pages**.
3. Under "Build and deployment," set **Source** to "Deploy from a branch," pick your main branch and the `/ (root)` folder, then save.
4. GitHub gives you a URL like `https://<your-username>.github.io/cars-on-wheels/` — that's your live site. It can take a minute or two to go live after the first push.
5. If you want your own domain (e.g. carsonwheels.com) instead of the github.io one, add a `CNAME` file with your domain in it and point your domain's DNS at GitHub Pages — GitHub's docs walk through the exact records to add.

## Making other edits later
Anything in `index.html` is safe to hand-edit directly (text, prices, links, the booking form). Just don't touch `dist/styles.css` by hand — if you ever add a new Tailwind class to the HTML that isn't already used elsewhere on the page, you'll need to rebuild it:

```bash
npm install
npx tailwindcss -i ./src/input.css -o ./dist/styles.css --minify
```

If you're not adding new *kinds* of Tailwind classes (just changing text, numbers, links), you don't need to rebuild anything — the existing `dist/styles.css` already covers all the classes currently in the page.
