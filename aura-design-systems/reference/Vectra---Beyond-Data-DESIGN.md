---
version: "alpha"
name: "Vectra - Beyond Data"
description: "Vectra Beyond Dashboard Section is designed for demonstrating application workflows and interface hierarchy. Key features include clear information density, modular panels, and interface rhythm. It is suitable for product showcases, admin panels, and analytics experiences."
colors:
  primary: "#8BC3A8"
  secondary: "#BDE4D0"
  tertiary: "#8DBECB"
  neutral: "#27272A"
  background: "#27272A"
  surface: "#18181B"
  text-primary: "#F4F4F5"
  text-secondary: "#27272A"
  border: "#3F3F46"
  accent: "#8BC3A8"
typography:
  display-lg:
    fontFamily: "Playfair Display"
    fontSize: "60px"
    fontWeight: 400
    lineHeight: "60px"
    letterSpacing: "-0.025em"
  body-md:
    fontFamily: "Inter"
    fontSize: "10px"
    fontWeight: 300
    lineHeight: "12.5px"
spacing:
  base: "4px"
  sm: "1px"
  md: "4px"
  lg: "6px"
  xl: "15px"
  gap: "4px"
  card-padding: "32px"
  section-padding: "24px"
---

## Overview

- **Composition cues:**
  - Layout: Grid
  - Content Width: Bounded
  - Framing: Framed
  - Grid: Strong

## Colors

The color system uses dark mode with #8BC3A8 as the main accent and #27272A as the neutral foundation.

- **Primary (#8BC3A8):** Main accent and emphasis color.
- **Secondary (#BDE4D0):** Supporting accent for secondary emphasis.
- **Tertiary (#8DBECB):** Reserved accent for supporting contrast moments.
- **Neutral (#27272A):** Neutral foundation for backgrounds, surfaces, and supporting chrome.

- **Usage:** Background: #27272A; Surface: #18181B; Text Primary: #F4F4F5; Text Secondary: #27272A; Border: #3F3F46; Accent: #8BC3A8

- **Gradients:** bg-gradient-to-b from-zinc-800/40 to-transparent via-zinc-900/10, bg-gradient-to-b from-[#0A0A0A]/90 to-[#0A0A0A]/90 via-[#0A0A0A]/60, bg-gradient-to-b from-[#0A0A0A]/80 to-[#0A0A0A]/90 via-[#0A0A0A]/40

## Typography

Typography pairs Playfair Display for display hierarchy with Inter for supporting content and interface copy.

- **Display (`display-lg`):** Playfair Display, 60px, weight 400, line-height 60px, letter-spacing -0.025em.
- **Body (`body-md`):** Inter, 10px, weight 300, line-height 12.5px.

## Layout

Layout follows a grid composition with reusable spacing tokens. Preserve the grid, bounded structural frame before changing ornament or component styling. Use 4px as the base rhythm and let larger gaps step up from that cadence instead of introducing unrelated spacing values.

Treat the page as a grid / bounded composition, and keep that framing stable when adding or remixing sections.

- **Layout type:** Grid
- **Content width:** Bounded
- **Base unit:** 4px
- **Scale:** 1px, 4px, 6px, 15px, 16px, 32px, 48px
- **Section padding:** 24px, 32px
- **Card padding:** 32px
- **Gaps:** 4px, 8px, 16px

## Elevation & Depth

Depth is communicated through outlined, border contrast, and reusable shadow or blur treatments. Keep those recipes consistent across hero panels, cards, and controls so the page reads as one material system.

Surfaces should read as outlined first, with borders, shadows, and blur only reinforcing that material choice.

- **Surface style:** Outlined
- **Borders:** 1px #3F3F46; 1px #FFFFFF; 1px #27272A; 1px #D4D4D8

### Techniques
- **Gradient border shell:** Use a thin gradient border shell around the main card. Wrap the surface in an outer shell with 1px padding and a 0px radius. Drive the shell with linear-gradient(rgba(39, 39, 42, 0.4), rgba(24, 24, 27, 0.1), rgba(0, 0, 0, 0)) so the edge reads like premium depth instead of a flat stroke. Keep the actual stroke understated so the gradient shell remains the hero edge treatment. Inset the real content surface inside the wrapper with a slightly smaller radius so the gradient only appears as a hairline frame.

## Shapes

Shapes rely on a tight radius system anchored by 9999px and scaled across cards, buttons, and supporting surfaces. Icon geometry should stay compatible with that soft-to-controlled silhouette.

Use the radius family intentionally: larger surfaces can open up, but controls and badges should stay within the same rounded DNA instead of inventing sharper or pill-only exceptions.

- **Corner radii:** 9999px
- **Icon treatment:** Linear
- **Icon sets:** Solar

## Components

Component styling should inherit the shared button, icon, spacing, and surface rules instead of inventing one-off treatments. Favor a small family of repeatable patterns for actions, content containers, and fields.

### Iconography
- **Treatment:** Linear.
- **Sets:** Solar.

## Do's and Don'ts

Use these constraints to keep future generations aligned with the current system instead of drifting into adjacent styles.

### Do
- Do use the primary palette as the main accent for emphasis and action states.
- Do keep spacing aligned to the detected 4px rhythm.
- Do reuse the Outlined surface treatment consistently across cards and controls.
- Do keep corner radii within the detected 9999px family.

### Don't
- Don't introduce extra accent colors outside the core palette roles unless the page needs a new semantic state.
- Don't exceed the detected minimal motion intensity without a deliberate reason.

## Motion

Motion stays restrained and interface-led across text, layout, and scroll transitions. Easing favors ease. Scroll choreography uses GSAP ScrollTrigger for section reveals and pacing.

**Motion Level:** minimal

**Easings:** ease

**Scroll Patterns:** gsap-scrolltrigger