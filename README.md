# CardMax — UI/UX Redesign

A front-end course exercise: redesigning the CardMax gift-card exchange app from a
mobile screenshot into a responsive, mobile-first web UI that also holds up as a
real desktop dashboard.

**Live demo:** _add your Vercel URL here after deploying_

---

## About this redesign

The original app is a mobile screen for buying/selling gift cards for cash. This
redesign keeps the mobile layout and information hierarchy close to the original,
but:

- Introduces one consistent **signature UI element** — a die-cut "ticket stub"
  card (dashed perforation + circular notches) — used for the balance card, the
  promo banner, gift-card tiles, and the profile card. It ties the whole UI
  together and reinforces the product's actual job: trading a voucher for cash.
- Rebuilds the layout to be **genuinely responsive**, not just a stretched phone
  screen. Below `1024px` it's the original single-column, bottom-tab-bar mobile
  layout. At `1024px+` the bottom tab bar becomes a persistent left sidebar, quick
  actions go from a 2×2 grid to a 4-across row, the gift-card grid expands to
  4–5 columns, and a "top rates today" side panel appears — using the extra
  screen space for real content instead of just stretching things out.
- Fixes a few UX gaps in the original: rate numbers now show units (`₦1,343.52/$`
  instead of a bare number), tapping a gift card opens an in-place sell modal
  with a live payout calculation instead of navigating away, and the empty
  transactions state has real copy and a call to action instead of just an
  illustration.
- Uses **real brand favicons** (via a keyless Google favicon lookup) on each
  gift-card tile instead of placeholder logos, with a graceful fallback to a
  colored initials badge if a favicon fails to load.

## Tech stack

- Plain **HTML** — single file, no build step
- **Tailwind CSS** via CDN, with a small custom config for the color/type tokens
- A short custom CSS block for the ticket-stub/perforation effect
- **[Lucide](https://lucide.dev)** for icons, loaded via CDN
- Vanilla **JavaScript** for view switching, the sell modal, balance visibility
  toggle, and filter tab states — no framework
- Fonts: **Fraunces** (display/numbers), **Space Grotesk** (UI text), **IBM Plex
  Mono** (rates and reference codes), all via Google Fonts

## Project structure

```
.
├── index.html      # the entire app — markup, styles, and JS
└── README.md
```

Everything lives in `index.html` on purpose, since this is a course exercise
meant to be read top to bottom. It's straightforward to split into
`styles.css` / `app.js` later if you want to practice that separation.

## Running locally

No install, no build step. Either:

- Open `index.html` directly in a browser, or
- Serve it so relative behavior matches production:
  ```bash
  npx serve .
  # or
  python3 -m http.server
  ```

## Deploying to Vercel

1. Push this repo to GitHub.
2. In Vercel, **Add New → Project** and import the repo.
3. Framework preset: **Other** (it's a static file, no build command needed).
4. Leave the build command empty and the output directory as `.` — Vercel will
   serve `index.html` at the root automatically.
5. Deploy.

## Notes / attribution

- Gift-card logos are fetched at runtime from Google's public favicon service
  (`google.com/s2/favicons`) by brand domain — no logo assets are stored in this
  repo. For a real production app you'd license proper brand marks or use an
  authenticated logo API instead.
- This is a UI/UX exercise, not a functional product — the sell flow, balances,
  and transaction history are all front-end mock state with no backend.

## License

MIT — for course/portfolio use.
