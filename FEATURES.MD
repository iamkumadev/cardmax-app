# CardMax — Feature Log

Tracking what's shipped vs. proposed, since this template gets updated
incrementally rather than built once. Update this file whenever a feature
lands or a new idea comes up, so it doesn't only live in chat history.

## Shipped

- Mobile-first responsive layout (bottom tab bar → sidebar dashboard at `lg:`)
- Ticket-stub signature component (balance card, promo banner, gift tiles, profile card)
- Design system / style guide (`style-guide.html`) — color, type, spacing, component tokens
- Dark mode (class-based, system-preference default, persisted via `localStorage`)
- Brand-neutral card marks (deterministic monogram + palette color — no real logos/trademarks bundled)
- Sell flow: card type selection (**E-code vs. Physical card**)
  - E-code → card code text field
  - Physical → photo upload (drag-and-drop + file picker, client-side preview, up to 4 images)
- Live payout calculation in the sell modal
- Balance visibility toggle (blur/unblur)
- Transaction filter tabs + empty state with call to action
- Lucide icon system throughout

## Proposed / backlog

Not yet built — candidates for future passes. Not every item here will
necessarily ship; treat this as a working list, not a commitment.

- Full sell flow as its own page (multi-step: brand → type → details → review → confirm), not just a modal
- Auth screens: login, sign up, forgot password, OTP verification
- Onboarding (first-run, 2–3 steps)
- Transaction detail page (currently only the empty list exists)
- Notifications panel/page
- Settings page (payout method, security, preferences) — currently just link stubs on the Me view
- Landing/marketing page (for selling the template itself)
- Alternate color skins (2–3, beyond light/dark)
- Form validation states wired to real interactivity (currently styled in the style guide only)
- Toast/snackbar notification system wired into actions (sell submitted, withdrawal requested, etc.)
- Loading skeleton states wired into real async-feeling transitions
- 404 / error page
- Documentation page/PDF for buyers (customizing colors/fonts, swapping in real brand logos)
- WordPress theme conversion (component structure should stay consistent to make this mechanical)

## Notes for the WordPress conversion later

- Keep class naming and component structure consistent across new screens so each
  can become a template part without a rebuild.
- Keep theming on the CSS-variable system (`--paper`, `--ink`, `--emerald`, etc.) —
  this maps cleanly to Customizer/theme.json color settings later.
- Avoid JS patterns that assume a single static page; new screens should use the
  same repeatable card/list markup patterns already established.