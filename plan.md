# Campus Lost and Found — Implementation Plan

## Scope
A focused, full-stack mini-project for a university campus. The app supports the complete essential workflow: authenticated students create lost/found reports, browse/search/filter reports, manage their own reports, mark reports returned, and administrators moderate reports.

## Design direction

### Three candidate styles
- **Campus utility editorial** (0.07): a calm, structured bulletin-board interface with strong labels and readable density.
- **Friendly civic dashboard** (0.05): approachable cards, clear actions, and warm community-oriented feedback.
- **Minimal operations desk** (0.08): compact, high-contrast controls optimized for quick report entry and scanning.

### Chosen style: Campus utility editorial
- **Design Movement:** contemporary editorial utility design, inspired by campus noticeboards and wayfinding systems.
- **Core Principles:** clarity before decoration; status visible at a glance; low-friction reporting; trustworthy moderation.
- **Color Philosophy:** warm paper-like neutrals create a familiar campus-board feel, with navy for trust, teal for found/positive action, and coral for lost/attention states.
- **Layout Paradigm:** a wide, asymmetric workspace with an information-rich hero/search rail and a flexible report stream rather than a centered marketing grid.
- **Signature Elements:** small uppercase status labels, subtle paper grain/ruled dividers, and a compact “report a find” action block.
- **Interaction Philosophy:** every action should explain its result immediately through inline states and toast feedback; filters should feel like sorting a physical board.
- **Animation:** restrained 150–220ms fades and lift-on-hover for report cards; no decorative motion that delays task completion.
- **Typography System:** use a bold geometric sans for headings and a highly readable sans for body copy; create hierarchy with weight and tracking rather than excessive size.
- **Brand Essence:** the campus’s shared recovery desk for misplaced belongings; clear, useful, dependable.
- **Brand Voice:** direct and reassuring. Examples: “Find it. Post it. Bring it home.” and “Every report helps the right item find its owner.”
- **Wordmark & Logo:** a simple pin-and-check mark paired with a compact wordmark, represented in the interface by a small outlined pin icon and bold text.
- **Signature Brand Color:** deep campus navy.

## Implementation

- Keep the supplied React/Express/tRPC/Drizzle starter.
- Use the existing Manus OAuth flow for real application authentication.
- Extend the MySQL schema with an `items` table containing report type, item details, optional photo URL, status, moderation status, timestamps, and owner ID.
- Add typed tRPC procedures for listing/searching, fetching a report, creating, editing, deleting, and marking returned; add admin procedures for moderation and summary counts.
- Keep the initial version focused while supporting an optional JPG, PNG, or WebP item photo upload through the supplied managed storage helper; store the stable asset path in the item record.
- Use ownership checks in the server procedures; never rely only on hidden frontend buttons.
- Build a responsive single-page experience with sections for browse, report form, signed-in user reports, and admin moderation.
- Include `/manus-routes.json` with the page routes before starting the dev server.

## Project structure

- `client/src/pages/Home.tsx`: main browse/report/dashboard experience.
- `client/src/App.tsx`: route registration.
- `client/src/index.css`: visual system and responsive styles.
- `drizzle/schema.ts`: users and item-report tables.
- `server/db.ts`: database connection and item queries.
- `server/routers.ts`: public, authenticated, and admin tRPC procedures.
- `public/manus-routes.json`: route manifest.
- `TODO.md`: tracked outcome criteria.
