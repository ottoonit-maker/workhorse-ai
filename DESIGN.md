# Workhorse AI — Design System

## 1. Visual Theme & Atmosphere

Dark-mode-native marketing site for a blue-collar AI automation agency. The mood is **industrial premium** — clean, confident, and grounded. Not Silicon Valley sleek, not startup playful. Think a well-built tool: no decoration for decoration's sake, every element earns its space.

The dark canvas (`#080808`) is the native medium. Content emerges from darkness through careful luminance hierarchy. Rust red (`#b5341c`) is the signature accent — warm, bold, physical. Brass (`#8b6914`) appears sparingly as a secondary accent for highlights and proof points. The overall impression should be: "these people build real things for real businesses."

**Key Characteristics:**
- Dark-mode-native: `#080808` background, `#111111` cards, `#161616` elevated surfaces
- Warm accent system: rust red primary, brass secondary — no cool blues or purples
- Montserrat throughout — weight 800 for display, 700 for emphasis, 400-500 for body
- Noise texture overlay at ultra-low opacity (0.03) for tactile, non-digital feel
- Semi-transparent borders (`rgba(255,255,255,0.06)` to `rgba(255,255,255,0.10)`) for structure without noise
- Radial gradient accents behind hero — rust red glow, never flat
- Approachable copy, peer-to-peer tone, no jargon

## 2. Color Palette & Roles

### Background Surfaces
- **Canvas** (`#080808`): Deepest background. Page body, hero, sections.
- **Card** (`#111111`): Card backgrounds, form inputs, elevated containers.
- **Elevated** (`#161616`): Hover states, active cards, secondary surfaces.
- **Card Alt** (`#141414`): Alternate card shade for variety.

### Text & Content
- **Primary** (`#ffffff`): Headlines, nav logo, strong emphasis. Pure white is OK here — the warm accents prevent clinical feel.
- **Secondary** (`#c4beb8`): Body text, descriptions. Warm gray, not cool.
- **Muted** (`#a09890`): Captions, labels, de-emphasized content. Warm undertone.
- **Subtle** (`#666666`): Footer text, disabled states, timestamps.

### Brand & Accent
- **Rust Red** (`#b5341c`): Primary accent. CTAs, section labels, active states, accent borders.
- **Rust Glow** (`rgba(181, 52, 28, 0.15)`): Background glow behind hero, hover halos.
- **Rust Light** (`#e87a5a`): Eyebrow badges, lighter accent contexts.
- **Brass** (`#8b6914`): Secondary accent. Stat numbers, proof highlights, premium moments.

### Status & Feedback
- **Success** (`#22c55e`): "Live" badges, positive indicators.
- **Warning** (`#f59e0b`): "Coming Soon" badges, attention indicators.

### Border & Divider
- **Border** (`#222222`): Solid dark border for prominent separations.
- **Border Light** (`#1e1e1e`): Subtle solid border.
- **Border Glow** (`rgba(181, 52, 28, 0.15)`): Accent border for featured cards.
- **Transparent** (`rgba(255, 255, 255, 0.06)`): Default section dividers, subtle borders.

## 3. Typography Rules

### Font Family
- **Primary**: `Montserrat`, with fallbacks: `Inter, system-ui, -apple-system, sans-serif`
- **Secondary**: `Inter`, used for smaller body text and form inputs
- Google Fonts import: `Montserrat:wght@400;500;600;700;800;900` and `Inter:wght@400;500;600;700`

### Hierarchy

| Role | Font | Size | Weight | Line Height | Letter Spacing | Notes |
|------|------|------|--------|-------------|----------------|-------|
| Display XL | Montserrat | clamp(3rem, 7vw, 5.5rem) | 800 | 1.05 | -0.02em | Hero headline |
| Display | Montserrat | clamp(2rem, 4vw, 2.5rem) | 800 | 1.1 | -0.02em | Section titles |
| Heading 3 | Montserrat | 1.125rem | 700 | 1.3 | normal | Card titles, feature names |
| Body Large | Montserrat | 1.125rem | 400 | 1.7 | normal | Hero subtitle, section descriptions |
| Body | Montserrat | 1rem | 400 | 1.65 | normal | Standard text |
| Body Emphasis | Montserrat | 1rem | 600 | 1.65 | normal | Nav links, labels |
| Small | Montserrat | 0.875rem | 400-500 | 1.7 | normal | Card body text, FAQ answers |
| Caption | Montserrat | 0.8125rem | 500 | 1.4 | normal | Nav links, fine print |
| Label | Montserrat | 0.75rem | 700 | 1.4 | 0.1em | Section labels (uppercase), form labels |
| Micro | Montserrat | 0.6875rem | 600 | 1.4 | 0.1em | Tags, badges (uppercase) |
| Stat Number | Montserrat | clamp(2.2rem, 5vw, 3rem) | 800-900 | 1 | -0.02em | Proof bar numbers |

### Principles
- **800 is the signature weight**: Used for all display text and headlines. Creates the bold, confident, blue-collar feel.
- **No Playfair Display**: Dropped. Single font family keeps it clean and fast.
- **Warm text colors**: Body text uses `#c4beb8` (warm gray), never cool gray or blue-tinted.
- **Uppercase sparingly**: Only for section labels and small badges. Never for headlines or body.

## 4. Component Stylings

### Buttons

**Primary CTA**
- Background: `var(--accent)` (#b5341c)
- Text: `#ffffff`, weight 700, 0.875-0.9375rem
- Padding: 13px 22px (standard), 16px (full-width)
- Radius: 6px
- Hover: `opacity: 0.85`
- Transition: `opacity 0.2s ease`

**Secondary / Ghost CTA**
- Background: `transparent`
- Text: `#ffffff`, weight 600
- Border: `1px solid rgba(255,255,255,0.15)`
- Padding: 13px 22px
- Radius: 6px
- Hover: `background: rgba(255,255,255,0.05); border-color: rgba(255,255,255,0.25)`

**Nav CTA**
- Background: `var(--accent)`
- Text: `#ffffff`, weight 600, 0.8125rem
- Padding: 8px 16px
- Radius: 4px

### Cards

**Standard Card**
- Background: `var(--bg-card)` (#111111)
- Border: `1px solid var(--border)` (#222222)
- Radius: 8px
- Padding: 36px 32px
- Hover: `transform: translateY(-3px); box-shadow: 0 8px 32px rgba(0,0,0,0.4)`
- Transition: `all 0.25s ease`

**Accent Card (Pain Points)**
- Background: `linear-gradient(145deg, #161210 0%, #0f0d0b 100%)`
- Border: `1px solid rgba(181,52,28,0.15)`
- Border-left: `3px solid rgba(181,52,28,0.4)` (accent stripe)
- Hover: left border brightens to `rgba(181,52,28,0.7)`

**Featured Card (Case Study)**
- Background: `var(--bg-card)` with image header
- Border: `1px solid var(--border)`
- Radius: 8px
- Padding: 40px 36px (below image)

### Inputs & Forms
- Background: `#111111`
- Border: `1px solid #333333`
- Text: `#ffffff`, 0.9375rem, Montserrat
- Padding: 12px 14px
- Radius: 6px
- Focus: `border-color: var(--accent); box-shadow: 0 0 0 3px var(--accent-glow)`
- Placeholder: `var(--muted-light)` (#a09890)

### Badges

**Eyebrow Badge**
- Background: `rgba(181,52,28,0.18)`
- Border: `1px solid rgba(181,52,28,0.5)`
- Text: `#e87a5a`, 0.75rem, weight 700, uppercase, letter-spacing 0.1em
- Padding: 6px 14px
- Radius: 20px

**Status Badge (Live)**
- Dot: 8px circle, `#22c55e`
- Text: `#22c55e`, 0.6875rem, weight 600

**Status Badge (Coming Soon)**
- Dot: 8px circle, `#f59e0b`
- Text: `#f59e0b`, 0.6875rem, weight 600

### Navigation
- Fixed top, `rgba(8,8,8,0.7)` background, `backdrop-filter: blur(20px)`
- Height: 64px
- Logo: Montserrat 800, 0.9375rem, letter-spacing 0.05em. "AI" in accent color.
- Links: 0.8125rem, weight 500, `var(--muted)`. Hover: `var(--text)`.
- Mobile: hamburger icon triggers full-screen overlay nav

## 5. Layout Principles

### Spacing Scale
- Base: 4px
- Scale: 4, 8, 12, 16, 20, 24, 32, 48, 64, 80, 96
- Section vertical padding: 96px (desktop), 80px (mobile)
- Section header margin-bottom: 64px
- Card internal padding: 32px-36px
- Grid gap: 20px

### Grid & Container
- Max content width: 1100px
- Hero max width: 860px (text)
- Form max width: 520px
- FAQ max width: 720px
- Horizontal padding: 24px (desktop), 20px (mobile)

### Whitespace Philosophy
- Generous section padding — dark space IS the design
- Compressed headlines (tight line-height 1.05-1.1) with spacious surroundings
- No visible section dividers — the dark canvas provides natural separation
- Subtle `rgba(255,255,255,0.06)` borders only where structure is truly needed

## 6. Depth & Elevation

| Level | Treatment | Use |
|-------|-----------|-----|
| Canvas (0) | `#080808` flat | Page background |
| Surface (1) | `#111111` + `1px solid #222222` | Cards, form inputs |
| Elevated (2) | `#161616` or `rgba(255,255,255,0.05)` | Hover states, active tabs |
| Floating (3) | `box-shadow: 0 8px 32px rgba(0,0,0,0.4)` | Card hover lift, dropdowns |
| Overlay (4) | `rgba(8,8,8,0.97)` + `backdrop-filter: blur(20px)` | Mobile nav overlay |
| Glow (accent) | `box-shadow: 0 0 40px rgba(181,52,28,0.08)` | Featured elements, hero |

**Shadow Philosophy**: On this dark canvas, depth is communicated primarily through background luminance steps (#080808 → #111111 → #161616), not through shadows. Shadows appear only on hover/interaction as a "lift" effect. The accent glow (rust red at very low opacity) adds warmth and draws the eye to key elements.

## 7. Do's and Don'ts

### Do
- Use `#080808` as the native canvas — this is a dark-first design
- Keep accent usage intentional: rust red for CTAs and emphasis, brass for proof/stats
- Use Montserrat 800 for all headlines — it's the brand's signature weight
- Maintain warm undertones in all grays (`#c4beb8`, `#a09890`) — never cool/blue grays
- Add noise texture overlay at 0.03 opacity for tactile feel
- Use `translateY(-3px)` hover lifts on cards for subtle interactivity
- Keep copy peer-to-peer: brewery owner to brewery owner, no jargon
- Use real numbers and real results — specificity builds trust

### Don't
- Don't use cool grays, blues, or purples — the palette is warm/earth-toned
- Don't use Playfair Display or any serif fonts — the brand is sans-serif only
- Don't make it feel "techy" or "Silicon Valley" — the audience is non-technical
- Don't use gradients on buttons — solid accent color with opacity hover
- Don't add decorative elements without purpose — every element should earn its space
- Don't use stock photos or AI-generated images — only real brewery/business photos
- Don't over-animate — subtle fades and lifts only, nothing flashy
- Don't use more than 5 hashtags or social badges — the site isn't social media

## 8. Responsive Behavior

### Breakpoints
| Name | Width | Key Changes |
|------|-------|-------------|
| Mobile | <600px | Single column, compact padding (80px sections), stacked grids |
| Tablet | 600-768px | 2-column grids begin, nav links hidden |
| Desktop | >768px | Full layout, horizontal nav, 96px section padding |

### Touch Targets
- All buttons: minimum 44px height
- Nav links: adequate spacing (28px gap)
- Form inputs: 12px padding, full-width on mobile
- FAQ items: 18px vertical padding on summary

### Collapsing Strategy
- Hero: font-size scales via `clamp()`, tags wrap naturally
- Nav: horizontal links → hamburger menu at 768px → full-screen overlay
- Pain cards / automation tabs: grid → single column at 600px
- Stats bar: flex wrap, 2x2 grid on mobile, dividers hidden
- Form: full-width on mobile
- Steps (How It Works): horizontal → vertical, arrows rotate 90deg

## 9. Agent Prompt Guide

### Quick Color Reference
- Page background: `#080808`
- Card background: `#111111`
- Elevated surface: `#161616`
- Primary accent (CTA): `#b5341c`
- Accent glow: `rgba(181, 52, 28, 0.15)`
- Secondary accent: `#8b6914`
- Heading text: `#ffffff`
- Body text: `#c4beb8`
- Muted text: `#a09890`
- Border: `#222222`
- Subtle border: `rgba(255, 255, 255, 0.06)`
- Success green: `#22c55e`
- Warning amber: `#f59e0b`

### Example Component Prompts
- "Create a hero section on `#080808` with radial gradient glow (`rgba(181,52,28,0.25)`). Headline in Montserrat 800, `clamp(3rem, 7vw, 5.5rem)`, white, line-height 1.05, letter-spacing -0.02em. Subtitle in 1.125rem weight 400, `#c4beb8`. Primary CTA button (`#b5341c`, 6px radius, 13px 22px padding) and ghost button (transparent bg, `1px solid rgba(255,255,255,0.15)`, 6px radius)."
- "Build a card: `#111111` background, `1px solid #222222` border, 8px radius, 36px 32px padding. Title: Montserrat 700, 1.0625rem, white. Body: 0.875rem weight 400, `#c4beb8`. Hover: `translateY(-3px)` with `box-shadow: 0 8px 32px rgba(0,0,0,0.4)`."
- "Create a stat counter: number in Montserrat 900, `clamp(2.2rem, 5vw, 3rem)`, white. Label below in 0.78rem weight 500, `#c4beb8`. Vertical dividers between stats: `1px solid rgba(255,255,255,0.08)`, 48px tall."
- "Build mobile nav overlay: `rgba(8,8,8,0.97)` background with `backdrop-filter: blur(20px)`. Links: Montserrat 600, 1.5rem, white, centered, 48px min tap target. Close button top-right."
