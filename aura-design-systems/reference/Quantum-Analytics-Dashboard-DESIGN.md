---
version: "alpha"
name: "Quantum Analytics Dashboard"
description: "Quantum Analytics Dashboard Section is designed for demonstrating application workflows and interface hierarchy. Key features include clear information density, modular panels, and interface rhythm. It is suitable for product showcases, admin panels, and analytics experiences."
colors:
  primary: "#312E81"
  secondary: "#1E1B4B"
  tertiary: "#6366F1"
  neutral: "#060614"
  background: "#060614"
  surface: "#312E81"
  text-primary: "#EDEDED"
  text-secondary: "#C7D2FE"
  border: "#6366F1"
  accent: "#312E81"
typography:
  display-lg:
    fontFamily: "Geist"
    fontSize: "72px"
    fontWeight: 200
    lineHeight: "72px"
    letterSpacing: "-0.025em"
  body-md:
    fontFamily: "Geist"
    fontSize: "12px"
    fontWeight: 200
    lineHeight: "19.5px"
  label-md:
    fontFamily: "Geist"
    fontSize: "12px"
    fontWeight: 300
    lineHeight: "16px"
rounded:
  full: "9999px"
spacing:
  base: "6px"
  sm: "1px"
  md: "6px"
  lg: "8px"
  xl: "14px"
  gap: "8px"
  card-padding: "32px"
  section-padding: "32px"
components:
  button-primary:
    backgroundColor: "{colors.secondary}"
    textColor: "#EEF2FF"
    typography: "{typography.label-md}"
    rounded: "{rounded.full}"
    padding: "14px"
  card:
    backgroundColor: "{colors.neutral}"
    rounded: "24px"
    padding: "32px"
---

## Overview

- **Composition cues:**
  - Layout: Grid
  - Content Width: Bounded
  - Framing: Framed
  - Grid: Strong

## Colors

The color system uses dark mode with #312E81 as the main accent and #060614 as the neutral foundation.

- **Primary (#312E81):** Main accent and emphasis color.
- **Secondary (#1E1B4B):** Supporting accent for secondary emphasis.
- **Tertiary (#6366F1):** Reserved accent for supporting contrast moments.
- **Neutral (#060614):** Neutral foundation for backgrounds, surfaces, and supporting chrome.

- **Usage:** Background: #060614; Surface: #312E81; Text Primary: #EDEDED; Text Secondary: #C7D2FE; Border: #6366F1; Accent: #312E81

- **Gradients:** bg-gradient-to-b from-indigo-900/40 to-transparent, bg-[radial-gradient(var(--tw-gradient-stops))] from-indigo-900/30 to-transparent

## Typography

Typography relies on Geist across display, body, and utility text.

- **Display (`display-lg`):** Geist, 72px, weight 200, line-height 72px, letter-spacing -0.025em.
- **Body (`body-md`):** Geist, 12px, weight 200, line-height 19.5px.
- **Labels (`label-md`):** Geist, 12px, weight 300, line-height 16px.

## Layout

Layout follows a grid composition with reusable spacing tokens. Preserve the grid, bounded structural frame before changing ornament or component styling. Use 6px as the base rhythm and let larger gaps step up from that cadence instead of introducing unrelated spacing values.

Treat the page as a grid / bounded composition, and keep that framing stable when adding or remixing sections.

- **Layout type:** Grid
- **Content width:** Bounded
- **Base unit:** 6px
- **Scale:** 1px, 6px, 8px, 14px, 18px, 19.5px, 24px, 32px
- **Section padding:** 32px, 80px
- **Card padding:** 32px
- **Gaps:** 8px, 12px, 24px

## Elevation & Depth

Depth is communicated through outlined, border contrast, and reusable shadow or blur treatments. Keep those recipes consistent across hero panels, cards, and controls so the page reads as one material system.

Surfaces should read as outlined first, with borders, shadows, and blur only reinforcing that material choice.

- **Surface style:** Outlined
- **Borders:** 1px #6366F1; 1px #03030A; 1px #312E81; 1px #3730A3

### Techniques
- **Gradient border shell:** Use a thin gradient border shell around the main card. Wrap the surface in an outer shell with 1px padding and a 24px radius. Drive the shell with linear-gradient(rgba(49, 46, 129, 0.4), rgba(0, 0, 0, 0)) so the edge reads like premium depth instead of a flat stroke. Keep the actual stroke understated so the gradient shell remains the hero edge treatment. Inset the real content surface inside the wrapper with a slightly smaller radius so the gradient only appears as a hairline frame.

## Shapes

Shapes rely on a tight radius system anchored by 2px and scaled across cards, buttons, and supporting surfaces. Icon geometry should stay compatible with that soft-to-controlled silhouette.

Use the radius family intentionally: larger surfaces can open up, but controls and badges should stay within the same rounded DNA instead of inventing sharper or pill-only exceptions.

- **Corner radii:** 2px, 24px, 9999px
- **Icon treatment:** Linear
- **Icon sets:** Solar

## Components

Anchor interactions to the detected button styles. Reuse the existing card surface recipe for content blocks.

### Buttons
- **Primary:** background #1E1B4B, text #EEF2FF, radius 9999px, padding 14px, border 1px solid rgba(55, 48, 163, 0.5).

### Cards and Surfaces
- **Card surface:** background #060614, border 1px solid rgb(3, 3, 10), radius 24px, padding 32px, shadow none.

### Iconography
- **Treatment:** Linear.
- **Sets:** Solar.

## Do's and Don'ts

Use these constraints to keep future generations aligned with the current system instead of drifting into adjacent styles.

### Do
- Do use the primary palette as the main accent for emphasis and action states.
- Do keep spacing aligned to the detected 6px rhythm.
- Do reuse the Outlined surface treatment consistently across cards and controls.
- Do keep corner radii within the detected 2px, 24px, 9999px family.

### Don't
- Don't introduce extra accent colors outside the core palette roles unless the page needs a new semantic state.
- Don't exceed the detected moderate motion intensity without a deliberate reason.

## Motion

Motion feels controlled and interface-led across text, layout, and section transitions. Timing clusters around 300ms and 500ms. Easing favors ease and cubic-bezier(0.4. Hover behavior focuses on color changes. Scroll choreography uses GSAP ScrollTrigger and Parallax for section reveals and pacing.

**Motion Level:** moderate

**Durations:** 300ms, 500ms, 700ms, 150ms

**Easings:** ease, cubic-bezier(0.4, 0, 0.2, 1)

**Hover Patterns:** color

**Scroll Patterns:** gsap-scrolltrigger, parallax

## WebGL

Reconstruct the graphics as a wide scene band using webgl, renderer, alpha, antialias, dpr clamp. The effect should read as retro-futurist, technical, and meditative: dot-matrix particle field with green on black and sparse spacing. Build it from dot particles + soft depth fade so the effect reads clearly. Animate it as slow breathing pulse. Interaction can react to the pointer, but only as a subtle drift. Preserve dom fallback.

**Id:** webgl

**Label:** WebGL

**Stack:** ThreeJS, WebGL

**Insights:**
  - **Scene:**
    - **Value:** Wide scene band
  - **Effect:**
    - **Value:** Dot-matrix particle field
  - **Primitives:**
    - **Value:** Dot particles + soft depth fade
  - **Motion:**
    - **Value:** Slow breathing pulse
  - **Interaction:**
    - **Value:** Pointer-reactive drift
  - **Render:**
    - **Value:** WebGL, Renderer, alpha, antialias, DPR clamp

**Techniques:** Dot matrix, Breathing pulse, Pointer parallax, Noise fields, DOM fallback

**Code Evidence:**
  - **HTML reference:**
    - **Language:** html
    - **Snippet:**
      ```html
      <!-- WebGL Canvas for Animated Background -->
      <canvas id="glcanvas" class="absolute inset-0 w-full h-full pointer-events-none z-0 mix-blend-screen opacity-80"></canvas>

      <div class="relative z-10 pointer-events-none">
      ```
  - **JS reference:**
    - **Language:** js
    - **Snippet:**
      ```
      const initHeroWebGL = () => {
          const canvas = document.getElementById('glcanvas');
          if (!canvas) return;

          const parent = canvas.parentElement;
          const scene = new THREE.Scene();

          // Soft depth fade via fog (Updated for dark indigo)
      …
      ```
  - **Renderer setup:**
    - **Language:** js
    - **Snippet:**
      ```
      const camera = new THREE.PerspectiveCamera(60, parent.clientWidth / parent.clientHeight, 0.1, 100);
      camera.position.z = 12;

      const renderer = new THREE.WebGLRenderer({ canvas: canvas, alpha: true, antialias: true });
      renderer.setSize(parent.clientWidth, parent.clientHeight);
      renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));

      // Dot-matrix particle field setup
      ```
  - **Scene setup:**
    - **Language:** js
    - **Snippet:**
      ```
      const canvas = document.getElementById('glcanvas');
      if (!canvas) return;

      const parent = canvas.parentElement;
      const scene = new THREE.Scene();

      // Soft depth fade via fog (Updated for dark indigo)
      scene.fog = new THREE.FogExp2(0x050510, 0.05);
      ```

## ThreeJS

Reconstruct the Three.js layer as a wide scene band with layered spatial depth that feels retro-futurist, volumetric, and technical. Use alpha, antialias, dpr clamp renderer settings, perspective, ~60deg fov, plane + box geometry, meshstandardmaterial + pointsmaterial materials, and ambient + directional lighting. Motion should read as timeline-led reveals, with poster frame + dom fallback.

**Id:** threejs

**Label:** ThreeJS

**Stack:** ThreeJS, WebGL

**Insights:**
  - **Scene:**
    - **Value:** Wide scene band with layered spatial depth
  - **Render:**
    - **Value:** alpha, antialias, DPR clamp
  - **Camera:**
    - **Value:** Perspective, ~60deg FOV
  - **Lighting:**
    - **Value:** ambient + directional
  - **Materials:**
    - **Value:** MeshStandardMaterial + PointsMaterial
  - **Geometry:**
    - **Value:** plane + box
  - **Motion:**
    - **Value:** Timeline-led reveals

**Techniques:** PBR shading, Particle depth, Timeline beats, alpha, antialias, DPR clamp, Poster frame + DOM fallback

**Code Evidence:**
  - **HTML reference:**
    - **Language:** html
    - **Snippet:**
      ```html
      <!-- WebGL Canvas for Animated Background -->
      <canvas id="glcanvas" class="absolute inset-0 w-full h-full pointer-events-none z-0 mix-blend-screen opacity-80"></canvas>

      <div class="relative z-10 pointer-events-none">
      ```
  - **JS reference:**
    - **Language:** js
    - **Snippet:**
      ```
      const initHeroWebGL = () => {
          const canvas = document.getElementById('glcanvas');
          if (!canvas) return;

          const parent = canvas.parentElement;
          const scene = new THREE.Scene();

          // Soft depth fade via fog (Updated for dark indigo)
      …
      ```
  - **Renderer setup:**
    - **Language:** js
    - **Snippet:**
      ```
      const camera = new THREE.PerspectiveCamera(60, parent.clientWidth / parent.clientHeight, 0.1, 100);
      camera.position.z = 12;

      const renderer = new THREE.WebGLRenderer({ canvas: canvas, alpha: true, antialias: true });
      renderer.setSize(parent.clientWidth, parent.clientHeight);
      renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));

      // Dot-matrix particle field setup
      ```
  - **Scene setup:**
    - **Language:** js
    - **Snippet:**
      ```
      const canvas = document.getElementById('glcanvas');
      if (!canvas) return;

      const parent = canvas.parentElement;
      const scene = new THREE.Scene();

      // Soft depth fade via fog (Updated for dark indigo)
      scene.fog = new THREE.FogExp2(0x050510, 0.05);
      ```