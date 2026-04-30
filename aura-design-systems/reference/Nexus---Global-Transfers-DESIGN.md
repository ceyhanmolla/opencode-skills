---
version: "alpha"
name: "Nexus - Global Transfers"
description: "Nexus Global Hero Section is designed for introducing a product with clear above-the-fold messaging. Key features include headline hierarchy, supporting copy, and a primary call-to-action. It is suitable for homepage hero areas and campaign landing pages."
colors:
  primary: "#F2EAD3"
  secondary: "#F68B1F"
  tertiary: "#10B981"
  neutral: "#FFFFFF"
  background: "#FFFFFF"
  surface: "#F2EAD3"
  text-primary: "#FFFFFF"
  text-secondary: "#F2EAD3"
  border: "#FFFFFF"
  accent: "#F2EAD3"
typography:
  display-lg:
    fontFamily: "Playfair Display"
    fontSize: "214.88px"
    fontWeight: 400
    lineHeight: "214.88px"
    letterSpacing: "-0.05em"
  body-md:
    fontFamily: "Inter"
    fontSize: "14px"
    fontWeight: 400
    lineHeight: "20px"
rounded:
  md: "0px"
  full: "9999px"
spacing:
  base: "4px"
  sm: "1px"
  md: "2px"
  lg: "4px"
  xl: "6px"
  gap: "6px"
  card-padding: "9px"
  section-padding: "32px"
components:
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "#000000"
    typography: "{typography.body-md}"
    rounded: "{rounded.full}"
    padding: "8px"
  button-secondary:
    textColor: "{colors.neutral}"
    typography: "{typography.body-md}"
    rounded: "{rounded.full}"
    padding: "12px"
  button-link:
    textColor: "{colors.neutral}"
    typography: "{typography.body-md}"
    rounded: "{rounded.md}"
    padding: "0px"
---

## Overview

- **Composition cues:**
  - Layout: Grid
  - Content Width: Full Bleed
  - Framing: Glassy
  - Grid: Strong

## Colors

The color system uses dark mode with #F2EAD3 as the main accent and #FFFFFF as the neutral foundation.

- **Primary (#F2EAD3):** Main accent and emphasis color.
- **Secondary (#F68B1F):** Supporting accent for secondary emphasis.
- **Tertiary (#10B981):** Reserved accent for supporting contrast moments.
- **Neutral (#FFFFFF):** Neutral foundation for backgrounds, surfaces, and supporting chrome.

- **Usage:** Background: #FFFFFF; Surface: #F2EAD3; Text Primary: #FFFFFF; Text Secondary: #F2EAD3; Border: #FFFFFF; Accent: #F2EAD3

- **Gradients:** bg-gradient-to-br from-white/30 to-transparent via-white/5, bg-gradient-to-tr from-transparent to-white/[0.12] via-white/[0.05], bg-gradient-to-l from-white/[0.05] to-transparent

## Typography

Typography pairs Playfair Display for display hierarchy with Inter for supporting content and interface copy.

- **Display (`display-lg`):** Playfair Display, 214.88px, weight 400, line-height 214.88px, letter-spacing -0.05em.
- **Body (`body-md`):** Inter, 14px, weight 400, line-height 20px.

## Layout

Layout follows a grid composition with reusable spacing tokens. Preserve the grid, full bleed structural frame before changing ornament or component styling. Use 4px as the base rhythm and let larger gaps step up from that cadence instead of introducing unrelated spacing values.

Treat the page as a grid / full bleed composition, and keep that framing stable when adding or remixing sections.

- **Layout type:** Grid
- **Content width:** Full Bleed
- **Base unit:** 4px
- **Scale:** 1px, 2px, 4px, 6px, 8px, 12px, 14px, 20px
- **Section padding:** 32px, 48px, 64px, 80px
- **Card padding:** 9px, 32px, 48px
- **Gaps:** 6px, 8px, 16px, 20px

## Elevation & Depth

Depth is communicated through glass, border contrast, and reusable shadow or blur treatments. Keep those recipes consistent across hero panels, cards, and controls so the page reads as one material system.

Surfaces should read as glass first, with borders, shadows, and blur only reinforcing that material choice.

- **Surface style:** Glass
- **Borders:** 1px #FFFFFF; 1px #000000
- **Shadows:** rgba(0, 0, 0, 0) 0px 0px 0px 0px, rgba(0, 0, 0, 0) 0px 0px 0px 0px, rgba(0, 0, 0, 0.035) 0px 2.8px 2.2px 0px, rgba(0, 0, 0, 0.047) 0px 6.7px 5.3px 0px, rgba(0, 0, 0, 0.06) 0px 12.5px 10px 0px, rgba(0, 0, 0, 0.07) 0px 22.3px 17.9px 0px, rgba(0, 0, 0, 0.086) 0px 41.8px 33.4px 0px, rgba(0, 0, 0, 0.12) 0px 100px 80px 0px; rgba(255, 255, 255, 0.02) 0px 0px 40px 0px inset; rgba(0, 0, 0, 0) 0px 0px 0px 0px, rgba(0, 0, 0, 0) 0px 0px 0px 0px, rgba(255, 255, 255, 0.05) 0px 0px 10px 0px inset
- **Blur:** 4px

### Techniques
- **Gradient border shell:** Use a thin gradient border shell around the main card. Wrap the surface in an outer shell with 1px padding and a 24px radius. Drive the shell with linear-gradient(to right bottom, rgba(255, 255, 255, 0.3), rgba(255, 255, 255, 0.05), rgba(0, 0, 0, 0)) so the edge reads like premium depth instead of a flat stroke. Keep the actual stroke understated so the gradient shell remains the hero edge treatment. Inset the real content surface inside the wrapper with a slightly smaller radius so the gradient only appears as a hairline frame.

## Shapes

Shapes rely on a tight radius system anchored by 6px and scaled across cards, buttons, and supporting surfaces. Icon geometry should stay compatible with that soft-to-controlled silhouette.

Use the radius family intentionally: larger surfaces can open up, but controls and badges should stay within the same rounded DNA instead of inventing sharper or pill-only exceptions.

- **Corner radii:** 6px, 24px, 9999px
- **Icon treatment:** Linear
- **Icon sets:** Solar

## Components

Anchor interactions to the detected button styles.

### Buttons
- **Primary:** background #F2EAD3, text #000000, radius 9999px, padding 8px, border 0px solid rgb(229, 231, 235).
- **Secondary:** text #FFFFFF, radius 9999px, padding 12px, border 1px solid rgba(255, 255, 255, 0.1).
- **Links:** text #FFFFFF, radius 0px, padding 0px, border 0px solid rgb(229, 231, 235).

### Iconography
- **Treatment:** Linear.
- **Sets:** Solar.

## Do's and Don'ts

Use these constraints to keep future generations aligned with the current system instead of drifting into adjacent styles.

### Do
- Do use the primary palette as the main accent for emphasis and action states.
- Do keep spacing aligned to the detected 4px rhythm.
- Do reuse the Glass surface treatment consistently across cards and controls.
- Do keep corner radii within the detected 6px, 24px, 9999px family.

### Don't
- Don't introduce extra accent colors outside the core palette roles unless the page needs a new semantic state.
- Don't mix unrelated shadow or blur recipes that break the current depth system.
- Don't exceed the detected moderate motion intensity without a deliberate reason.

## Motion

Motion feels controlled and interface-led across text, layout, and section transitions. Timing clusters around 150ms and 1000ms. Easing favors ease and 0. Hover behavior focuses on text and color changes. Scroll choreography uses GSAP ScrollTrigger for section reveals and pacing.

**Motion Level:** moderate

**Durations:** 150ms, 1000ms, 2000ms

**Easings:** ease, 0, 1), cubic-bezier(0.4, 0.2, cubic-bezier(0

**Hover Patterns:** text, color, transform

**Scroll Patterns:** gsap-scrolltrigger