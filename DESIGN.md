---
name: Efficient Support Interface
colors:
  surface: '#f8f9ff'
  surface-dim: '#cbdbf5'
  surface-bright: '#f8f9ff'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#eff4ff'
  surface-container: '#e5eeff'
  surface-container-high: '#dce9ff'
  surface-container-highest: '#d3e4fe'
  on-surface: '#0b1c30'
  on-surface-variant: '#464555'
  inverse-surface: '#213145'
  inverse-on-surface: '#eaf1ff'
  outline: '#777587'
  outline-variant: '#c7c4d8'
  surface-tint: '#4c42e9'
  primary: '#493ee5'
  on-primary: '#ffffff'
  primary-container: '#635bff'
  on-primary-container: '#fefaff'
  inverse-primary: '#c3c0ff'
  secondary: '#006e2f'
  on-secondary: '#ffffff'
  secondary-container: '#6bff8f'
  on-secondary-container: '#007432'
  tertiary: '#984100'
  on-tertiary: '#ffffff'
  tertiary-container: '#bf5300'
  on-tertiary-container: '#fffaf8'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#e2dfff'
  primary-fixed-dim: '#c3c0ff'
  on-primary-fixed: '#0f0069'
  on-primary-fixed-variant: '#321ed2'
  secondary-fixed: '#6bff8f'
  secondary-fixed-dim: '#4ae176'
  on-secondary-fixed: '#002109'
  on-secondary-fixed-variant: '#005321'
  tertiary-fixed: '#ffdbca'
  tertiary-fixed-dim: '#ffb690'
  on-tertiary-fixed: '#341100'
  on-tertiary-fixed-variant: '#783200'
  background: '#f8f9ff'
  on-background: '#0b1c30'
  surface-variant: '#d3e4fe'
typography:
  display-lg:
    fontFamily: Plus Jakarta Sans
    fontSize: 32px
    fontWeight: '700'
    lineHeight: 40px
    letterSpacing: -0.02em
  headline-md:
    fontFamily: Plus Jakarta Sans
    fontSize: 24px
    fontWeight: '600'
    lineHeight: 32px
  title-sm:
    fontFamily: Plus Jakarta Sans
    fontSize: 18px
    fontWeight: '600'
    lineHeight: 24px
  body-md:
    fontFamily: Plus Jakarta Sans
    fontSize: 14px
    fontWeight: '400'
    lineHeight: 20px
  body-sm:
    fontFamily: Plus Jakarta Sans
    fontSize: 12px
    fontWeight: '400'
    lineHeight: 16px
  label-bold:
    fontFamily: Plus Jakarta Sans
    fontSize: 12px
    fontWeight: '600'
    lineHeight: 16px
  metric-lg:
    fontFamily: Plus Jakarta Sans
    fontSize: 28px
    fontWeight: '700'
    lineHeight: 32px
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  container-padding: 24px
  gutter: 20px
  card-gap: 16px
  sidebar-width: 260px
  base-unit: 4px
---

## Brand & Style

This design system is built for high-performance SaaS environments, specifically support dashboards where data density must coexist with visual clarity. The brand personality is professional, efficient, and reliable. It utilizes a **Corporate / Modern** style that leans into "Soft UI" principles—combining clean whitespace with subtle tonal depth to create an interface that feels organized and approachable.

The target audience consists of support agents and managers who require quick data synthesis. The emotional response is one of "ordered calm"—reducing the stress of high ticket volumes through logical grouping, soft edges, and a refreshing, nature-inspired secondary color palette.

## Colors

The palette is anchored by a deep **Indigo Purple** primary, used for brand presence, primary actions, and key data visualizations. It is balanced by a vibrant **Emerald Green** for success states, "solved" metrics, and primary call-to-action buttons (like CSV exports). 

- **Primary (Indigo):** Used for navigation highlights, active chart states, and primary branding.
- **Secondary (Green):** Reserved for growth indicators, positive sentiment, and high-priority action buttons.
- **Accents (Orange/Blue/Yellow):** Used sparingly in charts to differentiate data categories without overwhelming the user.
- **Neutrals:** A sophisticated range of cool grays. Surfaces use a very light tint (`#F8FAFC`) to separate the background from the pure white (`#FFFFFF`) card containers.

## Typography

The design system utilizes **Plus Jakarta Sans** for its modern, geometric construction that remains highly legible at small sizes. The typographic hierarchy emphasizes "Metric" visibility, using bold weights for numerical data to ensure agents can scan key performance indicators instantly.

- **Headlines:** Use a tighter letter-spacing and bold weights to ground each dashboard section.
- **Data Labels:** Use a medium-gray neutral color to provide context without competing with the primary data points.
- **Mobile Considerations:** For screen widths below 768px, `display-lg` scales down to `24px` to maintain visual balance within condensed card layouts.

## Layout & Spacing

The layout follows a **Fixed Sidebar + Fluid Canvas** model. The sidebar is a steady anchor on the left, while the main content area utilizes a sophisticated card-based grid that adapts to the viewport.

- **Grid System:** A 12-column grid is used for the main canvas. Metric cards typically span 3 columns, while complex charts span 6 or 8 columns.
- **Rhythm:** An 8px linear scale governs the spacing. Standard card internal padding is `24px` (3 units) to create a sense of breathability amidst dense data.
- **Responsive Behavior:** On tablet devices, 3-column metrics collapse into a 2x2 grid. On mobile, all cards stack vertically with a reduced outer margin of `16px`.

## Elevation & Depth

This design system rejects heavy shadows in favor of **Tonal Layering** and low-contrast definition. Depth is created through subtle color shifts rather than physical light metaphors.

- **Background:** A soft off-white/gray base layer (`#F1F5F9`).
- **Cards:** Pure white (`#FFFFFF`) surfaces that sit "on top" of the background.
- **Borders:** Instead of shadows, cards use a `1px` solid border in a very light neutral (`#E2E8F0`) to define edges.
- **Interactive States:** Hovering over a card or list item triggers a subtle lift, usually represented by a very soft, high-diffusion shadow (0px 4px 12px rgba(0,0,0,0.05)) or a slight background tint change.

## Shapes

The shape language is consistently **Rounded**, which softens the analytical nature of the data. 

- **Cards & Large Containers:** Use a `12px` (0.75rem) corner radius.
- **Buttons & Inputs:** Use an `8px` (0.5rem) corner radius for a sturdy, clickable feel.
- **Charts:** Bar charts and progress rings should utilize rounded caps/corners to maintain the system's friendly visual language.
- **Tags/Status Indicators:** Use a fully rounded "pill" shape to distinguish them from interactive buttons.

## Components

### Buttons
Primary buttons use the Emerald Green background with white text. Secondary buttons use a ghost style (light gray border) or a subtle purple tint for internal navigation.

### Cards
Every dashboard module is contained within a white card. Cards must include a header section for the title and optional "View More" or "Filter" controls.

### Data Visualizations
- **Bar Charts:** Use grouped columns with a primary/secondary purple stack.
- **Status Rings:** Use a semi-circle gauge for "Ticket by Channel" with distinct colors for each category.
- **Sentiment Bars:** Use horizontal progress bars with red/orange/green color mapping for "Customer Satisfaction."

### Sidebar Navigation
Active states are indicated by a light indigo background wash and a thick vertical stroke on the far left or right of the menu item, paired with high-contrast icon colors.

### Input Fields
Search bars and dropdowns should use a light gray stroke and a clear placeholder icon. Focus states should utilize a `2px` indigo glow.