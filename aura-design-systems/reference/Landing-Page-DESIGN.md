---
version: "alpha"
name: "Landing Page"
description: "Product Promise Feature Section is designed for highlighting product capabilities and value points. Key features include reusable structure, responsive behavior, and production-ready presentation. It is suitable for component libraries and responsive product interfaces."
colors:
  primary: "#4B4BA0"
  secondary: "#D4D4D8"
  tertiary: "#8F47AE"
  neutral: "#D4D4D8"
  background: "#D4D4D8"
  surface: "#111111"
  text-primary: "#FFFFFF"
  text-secondary: "#71717A"
  border: "#A1A1AA"
  accent: "#4B4BA0"
typography:
  headline-lg:
    fontFamily: "System Font"
    fontSize: "24px"
    fontWeight: 500
    lineHeight: "32px"
    letterSpacing: "-0.025em"
  body-md:
    fontFamily: "System Font"
    fontSize: "14px"
    fontWeight: 300
    lineHeight: "20px"
spacing:
  base: "4px"
  sm: "1px"
  md: "4px"
  lg: "8px"
  xl: "12px"
  gap: "2px"
  card-padding: "12px"
  section-padding: "24px"
components:
  card:
    backgroundColor: "{colors.text-primary}"
    rounded: "12px"
    padding: "16px"
---

## Overview

- **Composition cues:**
  - Layout: Grid
  - Content Width: Bounded
  - Framing: Glassy
  - Grid: Strong

## Colors

The color system uses dark mode with #4B4BA0 as the main accent and #D4D4D8 as the neutral foundation.

- **Primary (#4B4BA0):** Main accent and emphasis color.
- **Secondary (#D4D4D8):** Supporting accent for secondary emphasis.
- **Tertiary (#8F47AE):** Reserved accent for supporting contrast moments.
- **Neutral (#D4D4D8):** Neutral foundation for backgrounds, surfaces, and supporting chrome.

- **Usage:** Background: #D4D4D8; Surface: #111111; Text Primary: #FFFFFF; Text Secondary: #71717A; Border: #A1A1AA; Accent: #4B4BA0

- **Gradients:** bg-gradient-to-b from-white/10 to-transparent

## Typography

Typography relies on System Font across display, body, and utility text.

- **Headlines (`headline-lg`):** System Font, 24px, weight 500, line-height 32px, letter-spacing -0.025em.
- **Body (`body-md`):** System Font, 14px, weight 300, line-height 20px.

## Layout

Layout follows a grid composition with reusable spacing tokens. Preserve the grid, bounded structural frame before changing ornament or component styling. Use 4px as the base rhythm and let larger gaps step up from that cadence instead of introducing unrelated spacing values.

Treat the page as a grid / bounded composition, and keep that framing stable when adding or remixing sections.

- **Layout type:** Grid
- **Content width:** Bounded
- **Base unit:** 4px
- **Scale:** 1px, 4px, 8px, 12px, 16px, 20px, 24px, 32px
- **Section padding:** 24px, 32px, 40px
- **Card padding:** 12px, 16px, 24px, 32px
- **Gaps:** 2px, 6px, 8px, 24px

## Elevation & Depth

Depth is communicated through glass, border contrast, and reusable shadow or blur treatments. Keep those recipes consistent across hero panels, cards, and controls so the page reads as one material system.

Surfaces should read as glass first, with borders, shadows, and blur only reinforcing that material choice.

- **Surface style:** Glass
- **Borders:** 2px #A1A1AA; 1px #D4D4D8
- **Shadows:** rgb(255, 255, 255) 0px 0px 0px 0px, rgb(17, 17, 17) 0px 0px 0px 2px, rgba(0, 0, 0, 0) 0px 0px 0px 0px; rgba(0, 0, 0, 0) 0px 0px 0px 0px, rgba(0, 0, 0, 0) 0px 0px 0px 0px, rgba(0, 0, 0, 0.035) 0px 2.8px 2.2px 0px, rgba(0, 0, 0, 0.047) 0px 6.7px 5.3px 0px, rgba(0, 0, 0, 0.06) 0px 12.5px 10px 0px, rgba(0, 0, 0, 0.07) 0px 22.3px 17.9px 0px, rgba(0, 0, 0, 0.086) 0px 41.8px 33.4px 0px, rgba(0, 0, 0, 0.12) 0px 100px 80px 0px; rgb(255, 255, 255) 0px 0px 0px 0px, rgba(0, 0, 0, 0.05) 0px 0px 0px 1px, rgba(0, 0, 0, 0.1) 0px 2px 3px -1px, rgba(25, 28, 33, 0.02) 0px 1px 0px 0px, rgba(25, 28, 33, 0.08) 0px 0px 0px 1px
- **Blur:** 4px

### Techniques
- **Gradient border shell:** Use a thin gradient border shell around the main card. Wrap the surface in an outer shell with 1px padding and a 16px radius. Drive the shell with linear-gradient(rgba(255, 255, 255, 0.1), rgba(0, 0, 0, 0)) so the edge reads like premium depth instead of a flat stroke. Keep the actual stroke understated so the gradient shell remains the hero edge treatment. Inset the real content surface inside the wrapper with a slightly smaller radius so the gradient only appears as a hairline frame.

## Shapes

Shapes rely on a tight radius system anchored by 8px and scaled across cards, buttons, and supporting surfaces. Icon geometry should stay compatible with that soft-to-controlled silhouette.

Use the radius family intentionally: larger surfaces can open up, but controls and badges should stay within the same rounded DNA instead of inventing sharper or pill-only exceptions.

- **Corner radii:** 8px, 12px, 15px, 16px, 9999px
- **Icon treatment:** Linear
- **Icon sets:** Solar

## Components

Reuse the existing card surface recipe for content blocks.

### Cards and Surfaces
- **Card surface:** background #FFFFFF, border 0px solid rgb(229, 231, 235), radius 12px, padding 16px, shadow rgb(255, 255, 255) 0px 0px 0px 0px, rgba(0, 0, 0, 0.05) 0px 0px 0px 1px, rgba(0, 0, 0, 0.1) 0px 2px 3px -1px, rgba(25, 28, 33, 0.02) 0px 1px 0px 0px, rgba(25, 28, 33, 0.08) 0px 0px 0px 1px.

### Iconography
- **Treatment:** Linear.
- **Sets:** Solar.

## Do's and Don'ts

Use these constraints to keep future generations aligned with the current system instead of drifting into adjacent styles.

### Do
- Do use the primary palette as the main accent for emphasis and action states.
- Do keep spacing aligned to the detected 4px rhythm.
- Do reuse the Glass surface treatment consistently across cards and controls.
- Do keep corner radii within the detected 8px, 12px, 15px, 16px, 9999px family.

### Don't
- Don't introduce extra accent colors outside the core palette roles unless the page needs a new semantic state.
- Don't mix unrelated shadow or blur recipes that break the current depth system.
- Don't exceed the detected minimal motion intensity without a deliberate reason.

## Motion

Motion stays restrained and interface-led across text, layout, and scroll transitions. Timing clusters around 25000ms. Easing favors ease and linear. Scroll choreography uses GSAP ScrollTrigger for section reveals and pacing.

**Motion Level:** minimal

**Durations:** 25000ms

**Easings:** ease, linear

**Scroll Patterns:** gsap-scrolltrigger