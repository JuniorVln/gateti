# Design System: Leitnium — For Builders
**Project:** `builder-energy` landing page
**File:** `builder-energy/index.html`

---

## 1. Visual Theme & Atmosphere

**Industrial Precision meets Luxury Restraint.**

The design communicates technical authority and unwavering certainty — the visual language of a firm that engineers, not assembles. The palette is almost entirely void-dark, with a single volcanic-ember accent that appears only where it means something. Nothing is decorative.

Sections alternate between deep charcoal darkness and warm off-white parchment, creating a rhythm of contrast that mirrors the product's own philosophy: dark where technical precision is foregrounded, warm where process and trust are being built. The overall density is **sparse and deliberate** — generous whitespace, ultra-tight typographic tracking, and micro-thin borders that suggest precision without ornamentation.

The mood: a premium engineering firm's pitch book — part industrial schematic, part luxury-residential confidence.

---

## 2. Color Palette & Roles

### Dark Surfaces
| Descriptive Name | Hex | Role |
|---|---|---|
| **Void Black** | `#0C0C0C` | Primary background, navbar, footer base, hero surface |
| **Carbon Deep** | `#111111` | Secondary section backgrounds (complaint, outcomes) |
| **Anthracite** | `#131313` | Card resting state background |
| **Graphite** | `#161616` | Card hover state background, system architecture section |

### Accent
| Descriptive Name | Hex | Role |
|---|---|---|
| **Ember Orange** | `#E8491C` | Primary brand color — CTAs, active states, eyebrow labels on dark, border accents, timeline alarm, hub block |
| **Hot Ember** | `#FF5C2A` | Hover state for Ember Orange buttons only |

### Light Surfaces
| Descriptive Name | Hex | Role |
|---|---|---|
| **Warm Parchment** | `#F0EDE7` | Light section background (Section 3 — assembled vs designed), body background on light |
| **Soft Sand** | `#E6E1D9` | Alternate light section (Section 5 — process) |
| **Stone Dust** | `#E0DDD6` | Card/panel background within light sections |
| **Warm Pebble** | `#D6D2CA` | Muted verdict bar background on light sections |
| **Cement** | `#D1CCC2` | Assembled-column item backgrounds (dashed card fill) |

### Text on Dark (White Opacity Scale)
| Descriptive Name | Opacity | Role |
|---|---|---|
| **Full White** | `white` | Primary headlines, active nav items, button labels |
| **Cream** | `white/70` | Body copy CTA area, footer paragraphs |
| **Silver Mist** | `white/60` | Body copy on dark sections |
| **Ash** | `white/50` | Secondary body copy, hero subtitle |
| **Smoke** | `white/40` | Tertiary descriptive copy, timeline body |
| **Ghost** | `white/30` | Footer nav links, decorative text |
| **Whisper** | `white/[0.18]` | Faded headline contrast text ("needs this." effect) |
| **Vapor** | `white/[0.06]` | Subtle section dividers, card borders |

### Text on Light
| Descriptive Name | Hex | Role |
|---|---|---|
| **Near Black** | `#0C0C0C` | Primary text on warm sections |
| **Graphite Mid** | `#444444` | Body copy within assembled diagram cards |
| **Concrete** | `#666666` | Step descriptions, secondary text on light |
| **Stone** | `#888888` | Eyebrow labels and muted labels on light |
| **Dashed Gray** | `#A8A49C` | Dashed borders in assembled comparison |
| **Mid Gray** | `#999999` | Section eyebrow on light |
| **Light Border** | `#CCCCCC` | Inactive step circle borders |

---

## 3. Typography Rules

**Font Family:** Inter (weights: Extralight, Light, Normal, Semibold, Extrabold, with Italic as a deliberate contrast tool)

### Hierarchy

**Display / Hero Headlines**
- `font-extrabold` + `tracking-[-0.045em]` + `leading-[0.95]`
- Extremely tight negative tracking — letters nearly touching, creating a compressed, precision-engineered feel
- Sizes: `text-6xl` → `text-8xl` → `text-9xl` (responsive upscaling)
- Contrast technique: one line rendered in `font-extralight italic` at reduced opacity to create visual breath within bold mass

**Section Headlines**
- Same tracking/leading formula as Display (`tracking-[-0.045em]`, `leading-[0.95]`)
- Sizes: `text-5xl` → `text-6xl` → `text-7xl`
- Same italic-and-opacity contrast technique used on key phrases

**Eyebrow / Section Labels**
- `font-semibold` + `tracking-[0.2em]` + `uppercase` + `text-xs`
- Maximum letter-spacing — creates a breath mark before each section
- Color: Ember Orange on dark, `#999999` or `#0C0C0C` on light, `white/40` for subdued labels

**Body Copy**
- `font-extralight` + `leading-[1.75]`
- Deliberately light weight — the content is authoritative, not the typography
- Opacity varies by importance: `/60` for primary body, `/50` for secondary, `/40` for tertiary

**Card Labels / UI Text**
- `font-semibold` for card titles and active states
- `font-light` or `font-normal` for secondary card descriptions
- `text-sm` or `text-xs` depending on density

**Inline Emphasis**
- Key phrases within light body copy are stepped up in opacity (e.g., `text-white/60` within `text-white/[0.38]` paragraphs)
- Never bold inline — only opacity differentiation

---

## 4. Component Stylings

### Buttons

**Primary Action (Pill CTA — Dark context)**
- Shape: Fully pill-shaped (`rounded-full`)
- Background: Ember Orange (`#E8491C`) → Hot Ember (`#FF5C2A`) on hover
- Text: `text-white font-semibold text-sm`
- Padding: `px-8 py-4` (standard) or `px-6 py-2.5` (compact nav version)
- Interaction: `hover:-translate-y-[1px]` — a 1px lift, no shadow added

**Secondary Action (Ghost Pill — Dark context)**
- Shape: Fully pill-shaped (`rounded-full`)
- Background: Transparent → `bg-white/5` on hover
- Border: `border border-white/20`
- Text: `text-white font-normal text-sm`
- Same 1px lift on hover

**Inverse Action (Dark button on Orange background)**
- Shape: Fully pill-shaped (`rounded-full`)
- Background: `#0C0C0C` → `#161616` on hover
- Text: `text-white font-semibold text-sm`
- Lift: `hover:-translate-y-[2px]` (2px for stronger interaction on orange background)

### Cards / Containers

**Outcome Cards (dark grid)**
- Background: Anthracite (`#131313`) at rest, Graphite (`#161616`) on hover
- Corners: Sharp — no border radius
- Top border: Transparent at rest, Ember Orange on hover (`hover:border-t-[#E8491C]`)
- Padding: `p-8 md:p-[44px]`
- Separation: `gap-[2px]` gap within a dark grid creates hairline separators without visible border

**Feature Callout Stripes (inline accents)**
- Left border: `border-l-2 border-[#E8491C]`
- Background: `bg-[#E8491C]/[0.08]` — near-invisible ember glow fill
- Padding: `px-4 py-3`
- No corner radius

**Architecture / Blueprint Panels**
- Border: `border border-white/10` or `border border-white/[0.06]`
- Background: `bg-white/[0.02]` — barely-there surface lift
- No radius — machine-precise rectangular form

**CTA Block**
- Background: Ember Orange (`#E8491C`) as full-bleed fill
- Radius: `rounded-[2px]` — almost square, just barely softened
- Overlay: subtle white grid pattern at `0.065` opacity for texture depth

**Assembled/Comparison Items (dashed)**
- Border: `border border-dashed border-[#A8A49C]`
- Background: `bg-[#D1CCC2]/50`
- No radius — deliberately unresolved, "assembled" aesthetic

### Icon Containers

**Small Icon Wells (UI diagram)**
- Size: `w-[30px] h-[30px]` circle (`rounded-full`)
- Background: `bg-white/[0.06]`
- Icon color: `text-white/80`

**Feature Icon Squares**
- Size: `w-[44px] h-[44px]`
- Border: `border border-[#E8491C]/30`
- No background fill, no radius — a precise square frame

**Step Circles (Process)**
- Size: `w-[70px] h-[70px]` pill (`rounded-full`)
- Active: `bg-[#E8491C]` with `text-white font-extrabold`
- Inactive: `bg-[#F0EDE7] border border-[#CCCCCC]` with `text-[#0C0C0C]/30 font-extrabold`
- Hover: `scale-[1.05]` lift

### Timeline Nodes
- Dot: `w-[13px] h-[13px] rounded-full`
- Inactive: `bg-[#111111] border border-white/20`
- Active/Alarm: `bg-[#E8491C] shadow-[0_0_12px_rgba(232,73,28,0.6)]` — pulsing ember glow
- Connecting track: `w-[1px] bg-white/10`
- Active row: left border `border-l-2 border-[#E8491C]` + `bg-[#E8491C]/[0.07]` fill

### Navigation
- Height: Fixed `h-[4rem]`
- Background: `bg-[#0C0C0C]/90 backdrop-blur-md`
- Bottom border: `border-b border-white/[0.06]`
- Links: `font-light text-white/70` → `text-white` on hover

### Footer
- Background: `#111111`
- Top border: `border-t border-white/[0.04]` — barely perceptible separator
- Column header labels: `text-xs font-semibold tracking-[0.2em] uppercase text-white/40`
- Links: `text-sm font-extralight text-white/60` → `text-white` on hover

---

## 5. Layout Principles

**Maximum Container Width:** `max-w-[90rem]` (1440px), centered with `px-6` horizontal padding

**Section Vertical Rhythm:** `py-[120px]` on mobile, `lg:py-[160px]` on desktop — generous breathing room between content zones

**Two-Column Grids:** `grid-cols-1 lg:grid-cols-2 gap-24` — major content blocks use 96px gap, giving each side room to breathe

**Tight Grid Separators:** Cards within a grid use `gap-[2px]` or `gap-[3px]` — hairline gaps that function as dividers without explicit border styling, maintaining a monolithic panel feel

**Decorative Architecture Lines:**
- Vertical accent line: `w-[1px]` gradient from transparent → Ember Orange → transparent, placed at `right-[30%]` in hero for asymmetric depth
- Subtle horizontal rule: `h-[1px] bg-white/[0.06]` at `bottom-[33%]`

**Background Texture:**
- Dark sections: `bg-grid-orange` — a 64px repeating grid with 4% opacity orange lines, adding subliminal engineering-blueprint texture
- CTA block: `bg-grid-white-subtle` — 32px grid at 6.5% white opacity

**Reveal Animations:**
- Elements enter with `opacity-0` + `translateY(16px)` → `opacity-1` + `translateY(0)`
- Easing: `cubic-bezier(0.16, 1, 0.3, 1)` — fast out, smooth landing (spring-like)
- Duration: `0.65s`
- Stagger delays: `delay-100`, `delay-200`, `delay-300` (100ms increments)

**Section Alternation Pattern:**
1. Dark (`#0C0C0C`) — Hero
2. Dark (`#111111`) — Risk/Timeline
3. Light (`#F0EDE7`) — Problem/Comparison
4. Dark (`#161616`) — Architecture
5. Light (`#E6E1D9`) — Process
6. Dark (`#111111`) — Outcomes
7. Dark (`#0C0C0C`) — Qualification
8. Dark (`#0C0C0C`) + Orange CTA block — Final CTA
9. Dark (`#111111`) — Footer

*The alternation is intentional: dark = technical authority, light = human trust-building.*

---

## 6. Depth & Elevation

The design is overwhelmingly **flat**. Shadow is a punctuation mark, not a texture.

- **Default state:** No shadow. Cards are distinguished by background color difference only.
- **Active/Alarm node:** `shadow-[0_0_12px_rgba(232,73,28,0.6)]` — a tight, glowing halo around the orange dot, conveying urgency
- **Architecture Hub (POWER BLOC):** `shadow-[0_0_40px_rgba(232,73,28,0.2)]` — a diffused ember corona that radiates importance without lifting the element
- **Backdrop blur on nav:** `backdrop-blur-md` — the only instance of blur, used to separate the fixed nav from page content during scroll

All elevation is achieved through color opacity and background contrast, not box shadows. This keeps the design feeling like precision technical drafting, not consumer UI.
