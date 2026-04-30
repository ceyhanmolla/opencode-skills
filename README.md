# OpenCode Skills

Premium OpenCode skills - ready-to-use design patterns, code examples, and reference guides.

## Quick Start

```bash
skill({ name: "skill-name" })
```

## Available Skills

### aura-design-systems

Automatically selects the best-matching design from 160+ reference design files. Analyzes project brief, presents options, and extracts complete design tokens (colors, typography, spacing, radius).

**Usage:**
```tsx
skill({ name: "aura-design-systems" })
```

**Workflow:**
1. Collect project details (type, industry, tone, colors)
2. Analyze reference designs and filter by tags
3. Present 2-3 best matches with reasoning
4. User selects → Extract all tokens

### hero-sections

Premium landing page sections with video backgrounds, glassmorphism, typography patterns, and animations. Includes Features, Testimonials, Stats, Pricing, CTA, and Footer sections.

**Files:**
- `SKILL.md` - Main reference + page structure
- `video-patterns.md` - Video integrations
- `liquid-glass.md` - Glassmorphism CSS
- `typography-patterns.md` - Font systems
- `animation-patterns.md` - Animations
- `features-sections.md` - Feature sections
- `testimonials.md` - Testimonial sections
- `stats-metrics.md` - Statistics sections
- `pricing.md` - Pricing sections
- `cta-footer.md` - CTA and Footer

**Usage:**
```tsx
skill({ name: "hero-sections" })
```

### frontend-ui-animator

Animations for Next.js + Tailwind + React projects. Hover effects, scroll animations, page transitions, and micro-interactions.

**Usage:**
```tsx
skill({ name: "frontend-ui-animator" })
```

### impeccable

Frontend interface design, polish, and critique. Covers UX review, visual hierarchy, typography, color, motion, accessibility, and more.

**Usage:**
```tsx
skill({ name: "impeccable" })
```

### shadcn-ui

Manages shadcn components - adding, searching, fixing, debugging, styling, and composing UI. Works with projects using `components.json`.

**Usage:**
```tsx
skill({ name: "shadcn-ui" })
```

### aura-asset-images

High-quality Unsplash-style images from Aura Asset Library.

**Usage:**
```tsx
skill({ name: "aura-asset-images" })
```

### video-to-website

Converts video content to website sections.

**Usage:**
```tsx
skill({ name: "video-to-website" })
```

## Technologies

- React 18+ / Next.js
- Tailwind CSS v3/v4
- TypeScript
- Framer Motion
- GSAP (optional)
- hls.js (video streaming)

## Contributing

1. Fork the repo
2. Create a new branch: `git checkout -b skill-name`
3. Commit changes: `git commit -m 'Add: new skill'`
4. Push: `git push origin skill-name`
5. Open a pull request

## License

MIT License