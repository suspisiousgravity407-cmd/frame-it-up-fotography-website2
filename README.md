# Frame It Up Fotography — Website

A premium, responsive website for Frame It Up Fotography (Coimbatore), built
with React + Vite + Tailwind CSS v4.

## Running the project

```bash
npm install
npm run dev       # local development, http://localhost:5173
npm run build     # production build -> dist/
npm run preview   # preview the production build locally
```

Requires Node.js 18+.

## Editing site content

Almost everything you'd want to change day-to-day lives in **one file**:

```
src/data/siteData.js
```

Open it and you'll find plain objects/arrays for:

- **`business`** — name, tagline, phone number, WhatsApp link, location,
  Instagram handle/URL, Google Maps link, email.
- **`nav`** — the navigation menu links.
- **`services`** — the 8 service/product cards (title, description, tag,
  image).
- **`galleryItems`** — the portfolio/gallery grid (image, category, caption).
- **`featuredWork`** — the two large "Featured Work" spotlights.
- **`whyChooseUs`** — the four "why choose us" blocks.
- **`instagramTiles`** — the static Instagram-style photo grid.

Change a piece of text or a phone number there and it updates everywhere on
the site automatically.

### Replacing the logo

Drop your new logo file into `src/assets/logo/` and update the reference in
`src/components/Navbar.jsx` and `src/components/Footer.jsx` (search for
`logo/logo-full.png`).

### Replacing photographs

Add new images into the matching subfolder of `src/assets/` (`hero/`,
`gallery/`, `products/`), then reference them by their relative path (e.g.
`"gallery/my-new-photo.jpg"`) inside `src/data/siteData.js`. The site resolves
these paths automatically — no import statements needed.

### Changing the phone number, location or Instagram

All three live at the top of `src/data/siteData.js` in the `business` object:

```js
export const business = {
  phone: "+91 82489 28404",
  phoneHref: "tel:+918248928404",
  location: "Coimbatore, Tamil Nadu, India",
  instagramHandle: "@frame_it_up_fotography",
  instagramUrl: "https://instagram.com/frame_it_up_fotography",
  ...
};
```

### Changing the business name

Update `business.name` and `business.shortName` in the same file, and the
`<title>` / meta tags at the top of `index.html`.

## Filling in the placeholders

Two things were intentionally left as clearly-marked placeholders because no
information was provided for them — search the codebase for these strings:

1. **About section founder/photographer bio** — `src/components/About.jsx`,
   the italic placeholder paragraph.
2. **Email address** — `business.email` in `src/data/siteData.js` is blank,
   which hides the mailto link in the Contact section and Footer. Fill it in
   to make the email link appear.

## Deploying

### Vercel
1. Push this project to a GitHub repository.
2. Go to vercel.com → **New Project** → import the repo.
3. Framework preset: **Vite**. Build command `npm run build`, output
   directory `dist`. Deploy.

### Netlify
1. Push to GitHub (or drag-and-drop the `dist/` folder after running
   `npm run build` at app.netlify.com/drop).
2. If connecting a repo: build command `npm run build`, publish directory
   `dist`.

### GitHub Pages
1. `npm install -D gh-pages`
2. Add to `package.json` scripts: `"deploy": "npm run build && gh-pages -d dist"`
3. Set `base: "/your-repo-name/"` in `vite.config.js`.
4. `npm run deploy`

## What's included

- Sticky, blur-on-scroll navbar with mobile hamburger menu
- Full-screen animated hero with your wedding-shoot photograph
- About, Services (8 cards), Portfolio gallery with keyboard-accessible
  lightbox (arrow keys + Escape), Featured Work spotlights, Why Choose Us,
  static Instagram grid, Contact section with click-to-call / WhatsApp /
  Google Maps links, and footer
- Scroll-reveal animations that respect `prefers-reduced-motion`
- Responsive down to small mobile screens
- Basic SEO: meta description, Open Graph tags, JSON-LD local-business
  schema, semantic headings, image alt text
