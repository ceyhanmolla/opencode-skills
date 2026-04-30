---
version: "alpha"
name: "Vertex - Scalable Systems For Tomorrow"
description: "Vertex Scalable Hero Section is designed for introducing a product with clear above-the-fold messaging. Key features include headline hierarchy, supporting copy, and a primary call-to-action. It is suitable for homepage hero areas and campaign landing pages."
colors:
  primary: "#00F0FF"
  secondary: "#000000"
  tertiary: "#0A45FF"
  neutral: "#000000"
  background: "#000000"
  surface: "#010A04"
  text-primary: "#FFFFFF"
  text-secondary: "#000000"
  border: "#FFFFFF"
  accent: "#00F0FF"
typography:
  display-lg:
    fontFamily: "Inter"
    fontSize: "96px"
    fontWeight: 300
    lineHeight: "96px"
    letterSpacing: "-0.05em"
  body-md:
    fontFamily: "Inter"
    fontSize: "16px"
    fontWeight: 200
    lineHeight: "24px"
  label-md:
    fontFamily: "Inter"
    fontSize: "14px"
    fontWeight: 300
    lineHeight: "20px"
rounded:
  md: "0px"
  full: "9999px"
spacing:
  base: "8px"
  sm: "1px"
  md: "8px"
  lg: "12px"
  xl: "14px"
  gap: "4px"
  section-padding: "32px"
components:
  button-primary:
    textColor: "{colors.text-primary}"
    typography: "{typography.label-md}"
    rounded: "{rounded.full}"
    padding: "8px"
  button-link:
    textColor: "{colors.text-primary}"
    typography: "{typography.label-md}"
    rounded: "{rounded.md}"
    padding: "0px"
---

## Overview

- **Composition cues:**
  - Layout: Grid
  - Content Width: Bounded
  - Framing: Glassy
  - Grid: Strong

## Colors

The color system uses dark mode with #00F0FF as the main accent and #000000 as the neutral foundation.

- **Primary (#00F0FF):** Main accent and emphasis color.
- **Secondary (#000000):** Supporting accent for secondary emphasis.
- **Tertiary (#0A45FF):** Reserved accent for supporting contrast moments.
- **Neutral (#000000):** Neutral foundation for backgrounds, surfaces, and supporting chrome.

- **Usage:** Background: #000000; Surface: #010A04; Text Primary: #FFFFFF; Text Secondary: #000000; Border: #FFFFFF; Accent: #00F0FF

- **Gradients:** bg-gradient-to-b from-transparent to-transparent via-white/[0.05], bg-gradient-to-t from-[#010a04] to-transparent, bg-gradient-to-b from-white/20 to-white/5, bg-gradient-to-b from-[#1a1a1a] to-black

## Typography

Typography relies on Inter across display, body, and utility text.

- **Display (`display-lg`):** Inter, 96px, weight 300, line-height 96px, letter-spacing -0.05em.
- **Body (`body-md`):** Inter, 16px, weight 200, line-height 24px.
- **Labels (`label-md`):** Inter, 14px, weight 300, line-height 20px.

## Layout

Layout follows a grid composition with reusable spacing tokens. Preserve the grid, bounded structural frame before changing ornament or component styling. Use 8px as the base rhythm and let larger gaps step up from that cadence instead of introducing unrelated spacing values.

Treat the page as a grid / bounded composition, and keep that framing stable when adding or remixing sections.

- **Layout type:** Grid
- **Content width:** Bounded
- **Base unit:** 8px
- **Scale:** 1px, 8px, 12px, 14px, 16px, 24px, 28px, 32px
- **Section padding:** 32px, 84px
- **Gaps:** 4px, 8px, 12px, 32px

## Elevation & Depth

Depth is communicated through glass, border contrast, and reusable shadow or blur treatments. Keep those recipes consistent across hero panels, cards, and controls so the page reads as one material system.

Surfaces should read as glass first, with borders, shadows, and blur only reinforcing that material choice.

- **Surface style:** Glass
- **Borders:** 1px #FFFFFF
- **Shadows:** rgba(0, 0, 0, 0) 0px 0px 0px 0px, rgba(0, 0, 0, 0) 0px 0px 0px 0px, rgba(0, 0, 0, 0.1) 0px 2px 3px -1px, rgba(25, 28, 33, 0.02) 0px 1px 0px 0px, rgba(25, 28, 33, 0.08) 0px 0px 0px 1px; rgba(0, 0, 0, 0) 0px 0px 0px 0px, rgba(0, 0, 0, 0) 0px 0px 0px 0px, rgba(255, 255, 255, 0.1) 0px 1px 0px 0px inset, rgba(255, 255, 255, 0.02) 0px -1px 0px 0px inset, rgba(0, 0, 0, 0.5) 0px 2px 4px 0px; rgba(0, 0, 0, 0) 0px 0px 0px 0px, rgba(0, 0, 0, 0) 0px 0px 0px 0px, rgba(0, 0, 0, 0.06) 0px 0px 0px 1px, rgba(0, 0, 0, 0.06) 0px 1px 1px -0.5px, rgba(0, 0, 0, 0.06) 0px 3px 3px -1.5px, rgba(0, 0, 0, 0.06) 0px 6px 6px -3px, rgba(0, 0, 0, 0.06) 0px 12px 12px -6px, rgba(0, 0, 0, 0.06) 0px 24px 24px -12px
- **Blur:** 12px

### Techniques
- **Gradient border shell:** Use a thin gradient border shell around the main card. Wrap the surface in an outer shell with 1px padding and a 9999px radius. Drive the shell with linear-gradient(rgb(255, 255, 255), rgb(212, 212, 212)) so the edge reads like premium depth instead of a flat stroke. Keep the actual stroke understated so the gradient shell remains the hero edge treatment. Inset the real content surface inside the wrapper with a slightly smaller radius so the gradient only appears as a hairline frame.

## Shapes

Shapes rely on a tight radius system anchored by 9999px and scaled across cards, buttons, and supporting surfaces. Icon geometry should stay compatible with that soft-to-controlled silhouette.

Use the radius family intentionally: larger surfaces can open up, but controls and badges should stay within the same rounded DNA instead of inventing sharper or pill-only exceptions.

- **Corner radii:** 9999px
- **Icon treatment:** Linear
- **Icon sets:** Solar

## Components

Anchor interactions to the detected button styles.

### Buttons
- **Primary:** text #FFFFFF, radius 9999px, padding 8px, border 0px solid rgb(229, 231, 235).
- **Links:** text #FFFFFF, radius 0px, padding 0px, border 0px solid rgb(229, 231, 235).

### Iconography
- **Treatment:** Linear.
- **Sets:** Solar.

## Do's and Don'ts

Use these constraints to keep future generations aligned with the current system instead of drifting into adjacent styles.

### Do
- Do use the primary palette as the main accent for emphasis and action states.
- Do keep spacing aligned to the detected 8px rhythm.
- Do reuse the Glass surface treatment consistently across cards and controls.
- Do keep corner radii within the detected 9999px family.

### Don't
- Don't introduce extra accent colors outside the core palette roles unless the page needs a new semantic state.
- Don't mix unrelated shadow or blur recipes that break the current depth system.
- Don't exceed the detected moderate motion intensity without a deliberate reason.

## Motion

Motion feels controlled and interface-led across text, layout, and section transitions. Timing clusters around 300ms. Easing favors ease and cubic-bezier(0.4. Hover behavior focuses on text and transform changes. Scroll choreography uses GSAP ScrollTrigger for section reveals and pacing.

**Motion Level:** moderate

**Durations:** 300ms

**Easings:** ease, cubic-bezier(0.4, 0, 0.2, 1)

**Hover Patterns:** text, transform

**Scroll Patterns:** gsap-scrolltrigger

## WebGL

Reconstruct the graphics as a full-bleed background field using webgl, renderer, alpha, dpr clamp, custom shaders. The effect should read as technical, meditative, and atmospheric: dot-matrix particle field with black and sparse spacing. Build it from dot particles + soft depth fade so the effect reads clearly. Animate it as slow breathing pulse. Interaction can react to the pointer, but only as a subtle drift. Preserve dom fallback.

**Id:** webgl

**Label:** WebGL

**Stack:** ThreeJS, WebGL

**Insights:**
  - **Scene:**
    - **Value:** Full-bleed background field
  - **Effect:**
    - **Value:** Dot-matrix particle field
  - **Primitives:**
    - **Value:** Dot particles + soft depth fade
  - **Motion:**
    - **Value:** Slow breathing pulse
  - **Interaction:**
    - **Value:** Pointer-reactive drift
  - **Render:**
    - **Value:** WebGL, Renderer, alpha, DPR clamp, custom shaders

**Techniques:** Dot matrix, Breathing pulse, Pointer parallax, Shader gradients, Noise fields

**Code Evidence:**
  - **HTML reference:**
    - **Language:** html
    - **Snippet:**
      ```html
      <div class="fixed inset-0 z-0 bg-[#010a04] pointer-events-none">
          <!-- Base: Three.js/WebGL Canvas -->
          <canvas id="bg-canvas" class="absolute inset-0 w-full h-full pointer-events-none"></canvas>

          <!-- Layer 1 (Geometry): Finer Diagonal hairline grid -->
      ```
  - **JS reference:**
    - **Language:** js
    - **Snippet:**
      ```
      });
      });

      // --- Three.js Greenish Glitch WebGL System ---
      const canvas = document.getElementById('bg-canvas');
      const renderer = new THREE.WebGLRenderer({ 
          canvas, 
          alpha: true,
      …
      ```
  - **Renderer setup:**
    - **Language:** js
    - **Snippet:**
      ```
      });

      // --- Three.js Greenish Glitch WebGL System ---
      const canvas = document.getElementById('bg-canvas');
      const renderer = new THREE.WebGLRenderer({ 
          canvas, 
          alpha: true, 
          antialias: false
      …
      ```
  - **Scene setup:**
    - **Language:** js
    - **Snippet:**
      ```
      delay: 0.2
          });
      });

      // --- Three.js Greenish Glitch WebGL System ---
      const canvas = document.getElementById('bg-canvas');
      const renderer = new THREE.WebGLRenderer({ 
          canvas,
      …
      ```

## ThreeJS

Reconstruct the Three.js layer as a full-bleed background field with layered spatial depth that feels technical. Use alpha, dpr clamp renderer settings, orthographic projection, plane geometry, shadermaterial materials, and ambient + key + rim lighting. Motion should read as timeline-led reveals, with poster frame + dom fallback.

**Id:** threejs

**Label:** ThreeJS

**Stack:** ThreeJS, WebGL

**Insights:**
  - **Scene:**
    - **Value:** Full-bleed background field with layered spatial depth
  - **Render:**
    - **Value:** alpha, DPR clamp
  - **Camera:**
    - **Value:** Orthographic projection
  - **Lighting:**
    - **Value:** ambient + key + rim
  - **Materials:**
    - **Value:** ShaderMaterial
  - **Geometry:**
    - **Value:** plane
  - **Motion:**
    - **Value:** Timeline-led reveals

**Techniques:** Shader materials, Timeline beats, alpha, DPR clamp, Poster frame + DOM fallback

**Code Evidence:**
  - **HTML reference:**
    - **Language:** html
    - **Snippet:**
      ```html
      <div class="fixed inset-0 z-0 bg-[#010a04] pointer-events-none">
          <!-- Base: Three.js/WebGL Canvas -->
          <canvas id="bg-canvas" class="absolute inset-0 w-full h-full pointer-events-none"></canvas>

          <!-- Layer 1 (Geometry): Finer Diagonal hairline grid -->
      ```
  - **JS reference:**
    - **Language:** js
    - **Snippet:**
      ```
      });
      });

      // --- Three.js Greenish Glitch WebGL System ---
      const canvas = document.getElementById('bg-canvas');
      const renderer = new THREE.WebGLRenderer({ 
          canvas, 
          alpha: true,
      …
      ```
  - **Renderer setup:**
    - **Language:** js
    - **Snippet:**
      ```
      });

      // --- Three.js Greenish Glitch WebGL System ---
      const canvas = document.getElementById('bg-canvas');
      const renderer = new THREE.WebGLRenderer({ 
          canvas, 
          alpha: true, 
          antialias: false
      …
      ```
  - **Scene setup:**
    - **Language:** js
    - **Snippet:**
      ```
      delay: 0.2
          });
      });

      // --- Three.js Greenish Glitch WebGL System ---
      const canvas = document.getElementById('bg-canvas');
      const renderer = new THREE.WebGLRenderer({ 
          canvas,
      …
      ```