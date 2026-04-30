---
version: "neuform-pro"
name: "Customer Insights"
description: "Customer Insights Menu Component is designed for building reusable UI components in modern web projects. Key features include reusable layout structure, responsive behavior, and production-ready styling. Built with custom CSS, it is suitable for component libraries and responsive product interfaces."
colors:
  primary: "#1E3A8A"
  secondary: "#030712"
  accent: "#581C87"
  background: "#030712"
  surface: "#18181B"
  text-primary: "#FFFFFF"
  text-secondary: "#A1A1AA"
  border: "#27272A"
typography:
  display-lg:
    fontFamily: "Inter"
    fontSize: "64px"
    fontWeight: 500
    lineHeight: "1.04"
    letterSpacing: "0"
  body-md:
    fontFamily: "Inter"
    fontSize: "16px"
    fontWeight: 400
    lineHeight: "1.6"
  label-md:
    fontFamily: "JetBrains Mono"
    fontSize: "12px"
    fontWeight: 600
    lineHeight: "1.2"
spacing:
  base: "8px"
  gap: "16px"
  card-padding: "24px"
  section-padding: "80px"
rounded:
  card: "15px"
  control: "15px"
  pill: "9999px"
components:
  card:
    background: "Use the surface token with subtle borders and HTML-matched shadow depth"
    radius: "Match the declared card radius token"
  button:
    background: "Use primary or accent colors for the main action"
    radius: "Use the control or pill radius based on the source HTML"
---
# Customer Insights
Source: Neuform Pro templates. Author: Meng To (@mengto). Views: 4; favorites: 0; remixes: 0.
Tags: footer, navigation, links, bento, animated, social-proof, effect, legal.
## Overview
Customer Insights Menu Component is designed for building reusable UI components in modern web projects. Key features include reusable layout structure, responsive behavior, and production-ready styling. Built with custom CSS, it is suitable for component libraries and responsive product interfaces.

NEXUS Menu 01 PERSPECTIVES What people say Discover how forward-thinking teams are leveraging our architecture to redefine their operational capabilities and scale with confidence. 02 EVALUATIONS Marcus Reed Systems Arc…
## Composition
Use the attached HTML reference as the source of truth. Preserve the visible hierarchy, first-screen composition, section rhythm, density, and interaction tone before adapting copy or content.
Key visible headings include: What people say; Marcus Reed; Elena Vance; Julian Silva.
## Colors
Anchor the palette in primary #1E3A8A, secondary #030712, accent #581C87, background #030712, surface #18181B, text-primary #FFFFFF. Keep background, surface, text, and border roles distinct so generated layouts retain the same contrast pattern as the source.
## Typography
Use Inter for display moments and Inter for body copy unless the HTML clearly demands a compatible fallback. Labels and technical metadata should use JetBrains Mono or an equivalent mono face.
## Layout
Keep spacing deliberate and stable. Favor the same grid direction, max-width behavior, card density, and responsive stacking seen in the HTML. Do not replace distinctive source structures with generic SaaS sections.
## Components
Cards, buttons, badges, navigation, and repeated blocks should preserve the source geometry, border treatment, and hover feel.
## Motion
Preserve existing motion cues such as masked reveals, staggered entrance, hover lift, scroll-triggered transitions, and ambient movement. Keep easing smooth and restrained.
## WebGL & Effects

If the source includes canvas, WebGL, Three.js, gradients, particles, or atmospheric effects, rebuild them as supporting layers behind the content. Keep effects performant, responsive, and secondary to the interface.

## Guardrails
- Do not flatten the source into a generic card grid.
- Do not swap the color mode unless the source clearly supports it.
- Preserve the first viewport signal, focal object, and visual density.
- Keep buttons, cards, and badges aligned to the same radius and border language.