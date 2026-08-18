# Help Desk Lite — UI Generation Prompt

Copy everything below the line into your UI tool, with `design.jpg` and `DESIGN_1_.md` attached.

---

Build a web application called **Help Desk Lite** — an internal support ticketing solution that helps institutions manage employee support requests, assign clear ownership, and maintain a transparent, organized workflow that reduces follow-up communication gaps.

## Design System (strict — do not invent tokens)

Use the attached `DESIGN_1_.md` as the single source of truth. Key values to apply exactly:

- **Font:** Plus Jakarta Sans across all text.
- **Primary:** `#493ee5` (indigo) — nav highlights, active states, primary data.
- **Secondary:** `#006e2f` on `#6bff8f` container (emerald) — success states, positive metrics, primary CTA buttons (e.g. "Export CSV").
- **Surfaces:** background `#f8f9ff`, cards `#ffffff`, borders `1px solid #c7c4d8` (outline-variant) instead of heavy shadows.
- **Radius:** cards/containers `12px`, buttons/inputs `8px`, status tags `full pill`.
- **Spacing:** `260px` fixed sidebar, `24px` card padding, `20px` gutter, `16px` card-gap, 8px rhythm scale.
- **Hover state:** soft lift via `0px 4px 12px rgba(0,0,0,0.05)` or a light background tint — never a hard shadow.
- **Focus state:** `2px` indigo glow on inputs.
- **Metrics typography:** bold `28px` (`metric-lg`) for headline numbers; `body-sm` gray for captions like "Compare to last month."

## Brand

Generate a minimal, geometric logo mark for **Help Desk Lite** using the indigo primary (`#493ee5`) with an optional emerald accent. It must stay legible at small sizes (~24px) for the top-left of the sidebar, in the same slot the reference design uses for its workspace logo + name.

## Layout Shell (apply to every page)

Reuse the exact shell from the reference image:

- **Left sidebar (260px, fixed):** logo + workspace name at top, global search bar below it, then the primary nav (see IA below), a "Favorites" section, a "Pinned Tickets" list with live status dots and quick-add, and a "Help & Support" link pinned at the bottom.
- **Top bar:** page title on the left (e.g. "Dashboard," "Inbox"), primary action button on the right where relevant (e.g. green "Export CSV" pill with a dropdown chevron, matching the reference).
- **Content canvas:** white cards on the `#f8f9ff` background, 12-column responsive grid — metric cards span 3 columns, charts span 6–8 columns, collapsing to 2×2 on tablet and stacking full-width on mobile with 16px outer margin.

## Information Architecture

1. **Dashboard (home)**
   - Row of 4 metric cards, styled exactly like the reference (value in `metric-lg` bold, a small colored % pill showing trend, "Compare to last month" caption below): **Open Tickets, Unassigned Tickets, Resolved Tickets, Average First Response Time.**
   - Two-column chart row: a grouped bar chart ("Tickets Created vs Resolved," last 7 days, with a date-range dropdown and a hover tooltip showing both values) beside a donut chart ("Tickets by First Reply Time," bucketed into time ranges with a color-coded legend and percentages).
   - Second chart row: a semicircle gauge ("Tickets by Channel" — e.g. Email, Chat, Web Form — with a total count in the center and a colored legend), beside a satisfaction panel (response count + Positive/Neutral/Negative rows, each with an icon, percentage, and horizontal progress bar in green/gray/red).
   - Recent activity feed at the bottom of the canvas (ticket created/assigned/resolved events, timestamped).

2. **Inbox** — incoming ticket messages grouped by unread/read, with priority tags (pill-shaped, color-coded: red=urgent, orange=high, gray=normal), sender avatar, preview line, and timestamp. Selecting a message opens a right-hand detail/reply panel.

3. **Notifications** — chronological list of system events (ticket assigned to you, status changed, comment added, SLA breach warning), each with an icon matching the event type, unread indicator (indigo dot), and relative timestamp. Include a "Mark all as read" action in the top bar.

4. **Tickets**
   - Full ticket table: filters across the top (Status, Assignee, Priority, Date range) as dropdown pills matching the input style in the design system.
   - Table rows show ticket ID, subject, requester, assignee avatar, status pill (Open/In Progress/Resolved — indigo/orange/green), priority pill, and last updated.
   - Clicking a row opens a **ticket detail view**: conversation thread, status/assignee/priority controls in a right sidebar, and an internal notes tab.

5. **Knowledge Base** — separate from ticket data. Category grid at the top (card per category, icon + article count), a prominent search bar, and a list/grid of articles below with title, category tag, and last-updated date.

## Authentication — Supabase

- Build **login** and **signup** screens using **Supabase Auth** (email/password, with the layout styled to match the design system's card and input conventions — white card on the `#f8f9ff` background, `8px` rounded inputs, indigo focus glow).
- Implement **role-based access** via Supabase Row Level Security: **Admin** role sees all tickets, all users, and a Reports/analytics view; **Employee** role sees only their own submitted tickets and the shared Knowledge Base.
- Show explicit **loading states** (button spinner, disabled state) and **error states** (inline red error text under the field, using the `error` token `#ba1a1a`) for both login and signup.
- Protect all five main routes behind an authenticated session; redirect unauthenticated users to login.

## Motion & Interaction (based on Emil Kowalski's animation principles)

Apply these rules precisely — do not default to generic "smooth" transitions.

**Easing:**
- Elements entering/exiting the screen (modals, dropdowns, drawers, toasts, the Inbox reply panel, the Ticket detail slide-over): `ease-out` (`cubic-bezier(0.215, 0.61, 0.355, 1)`).
- Elements already on screen that move or morph (sidebar active-state indicator sliding between items, tab underline, table row reordering after a filter/sort): `ease-in-out` (`cubic-bezier(0.645, 0.045, 0.355, 1)`).
- Hover and color transitions (card lift, button background, nav item highlight): `ease`, `150ms`.
- Never use `linear` except for constant-motion elements (e.g. a skeleton shimmer sweep) or `ease-in`.

**Duration:**
- Micro-interactions (button press, icon toggle): 100–150ms.
- Standard UI — dropdowns, tooltips, filter pills, notification toasts: 150–250ms.
- Modals, the ticket detail panel, the Inbox reply drawer: 200–300ms. Exit ~20% faster than entrance.
- Nothing in the interface exceeds 300ms.

**Paired elements:** any modal/overlay, dropdown/backdrop, or drawer/scrim pair must share identical duration and easing so they read as one unit (e.g. Ticket detail panel `transform 220ms ease-out` + its scrim `opacity 220ms ease-out`).

**Frequency rule:** the sidebar nav, table row hovers, and pill filters are seen 100+ times a day — keep these to a plain `background-color`/`transform` transition only, no entrance choreography. Reserve any "special" motion (e.g. a slightly springier feel) for rare moments: first login, empty states, a ticket being marked resolved.

**Micro-interaction details:**
- Buttons: `transform: scale(0.97)` on `:active`.
- Anything that "appears," like a dropdown or popover: animate from `scale(0.95)` and correct `transform-origin` (the trigger location), not from `scale(0)`.
- Skeleton loading (not spinners) for metric cards, charts, and table rows while data loads.

**Performance:** animate only `transform` and `opacity` — never `width`, `height`, `padding`, or `margin`. Add `will-change: transform` on elements prone to jitter (the ticket detail slide-over, dropdown menus).

**Glass/blur:** modals and dropdowns get an 8–12px backdrop blur behind the overlay (stay under 20px — expensive, especially in Safari), consistent with the design system's "ordered calm" feel. The blur fades in with the same `ease-out`/duration as the overlay itself, not as a separate animation.

**Accessibility:** every animated element ships with a matching `prefers-reduced-motion: reduce` rule that sets `animation: none` / `transition: none` — no exceptions, including opacity and color transitions. Hover-triggered animations (card lift, button scale) must be scoped to `@media (hover: hover) and (pointer: fine)` so they don't misfire on tap for mobile/tablet users.

## Constraints

- Keep the sidebar, top bar, spacing, and card conventions identical across all five sections — no section should introduce its own layout pattern.
- Where a section (Inbox, Notifications, Knowledge Base) isn't shown in the reference image, infer its styling strictly from the patterns that *are* shown (card shells, pill tags, avatar treatment, typography scale) rather than introducing new visual language.
- Do not use any color, radius, or spacing value not present in the attached design-system file.

---

**Suggested generation order:** Sidebar shell + logo + design tokens → Login/Signup (Supabase) → Dashboard → Tickets (list + detail) → Inbox → Notifications → Knowledge Base. Validate each stage against `DESIGN_1_.md` before generating the next.
