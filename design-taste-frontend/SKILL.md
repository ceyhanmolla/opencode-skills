---
name: design-taste-frontend
description: Use when building premium frontend interfaces, enforcing metric-based design rules and overriding default AI biases toward generic UI patterns
license: MIT
compatibility: opencode
metadata:
  audience: frontend-developers
  skill_type: design-principles
---

# Design Taste Frontend

Senior UI/UX Engineering. Architectural rules for premium digital interfaces.

## Active Baseline

| Metric | Default | Range |
|-------|---------|-------|
| DESIGN_VARIANCE | 8 | 1=Symmetric, 10=Artsy |
| MOTION_INTENSITY | 6 | 1=Static, 10=Cinematic |
| VISUAL_DENSITY | 4 | 1=Airy, 10=Cockpit |

Adapt dynamically based on user requests.

## Architecture Conventions

- **Dependency Check:** Always verify package.json before importing libraries
- **Framework:** React/Next.js default. Use Server Components (RSC) for static, Client for interactive
- **State:** Local useState/useReducer for isolated UI only
- **Styling:** Tailwind CSS 90%
- **Icons:** @phosphor-icons/react or @radix-ui/react-icons (check package.json)
- **NO EMOJIS:** Use icons or SVG primitives only

## Layout Rules

- **Viewport:** Use `min-h-[100dvh]` NOT `h-screen` (mobile stability)
- **Grid over Flex:** Use CSS Grid, not flexbox math
- **Breakpoints:** sm(640), md(768), lg(1024), xl(1280)
- **Container:** max-w-7xl mx-auto

## Anti-Slop Rules (Forbidden)

### Typography
- NO Inter font (use Geist, Outfit, Satoshi)
- NO massive H1s screaming hierarchy
- NO Serif on Dashboards (only creative/editorial)

### Color
- NO pure black (#000000)
- NO neon/outer glows
- NO AI Purple/Blue aesthetic
- Max 1 accent color, saturation < 80%

### Layout
- NO 3-column equal card rows
- NO centered Hero when variance > 4
- NO generic card containers when density > 7

### Content
- NO "John Doe", "Sarah Chan" names
- NO generic avatars (use realistic placeholders)
- NO predictable numbers (use organic: 47.2%, not 50%)

## Interactive States (Required)

- **Loading:** Skeletal loaders matching layout
- **Empty:** Composed empty states
- **Error:** Inline form errors
- **Active:** translate-y-[1px] or scale-[0.98] for tactile feedback

## Motion Rules

- **MOTION 1-3:** No auto-animation, hover/active only
- **MOTION 4-7:** CSS transitions, animation-delay cascades
- **MOTION 8-10:** Framer Motion hooks (NOT window scroll listeners)
- **Physics:** Spring (stiffness: 100, damping: 20), no linear easing

## Performance

- **Hardware:** Animate only transform/opacity
- **GPU filters:** Use on fixed, pointer-event-none only
- **Z-Index:** Strict layer contexts only (nav, modal, overlay)

## Creative Archetypes

### Navigation
- Mac Dock magnification
- Magnetic buttons (useMotionValue)
- Dynamic Island morphing
- Floating speed dial

### Layouts (Quick Ref)
| Pattern | Description |
|---------|------------|
| Bento Grid | Asymmetric tile grouping |
| Masonry | Staggered grid |
| Split Screen | 50/50 sliding halves |
| Chroma Grid | Animated color borders |

### Cards
| Pattern | Description |
|---------|------------|
| Parallax Tilt | 3D mouse tracking |
| Spotlight Border | Dynamic illumination |
| Glassmorphism | Frosted + inner refraction |
| Holographic Foil | Iridescent on hover |

### Scroll
| Pattern | Description |
|---------|------------|
| Sticky Stack | Cards stacking |
| Horizontal Pan | Vertical → horizontal |
| Zoom Parallax | Background zoom |
| Liquid Swipe | Viscous transition |

## Bento 2.0 Specification

When building SaaS dashboards:

- **Palette:** bg-slate-50, cards white, border-slate-200
- **Radius:** rounded-[2.5rem]
- **Shadow:** shadow-[0_20px_40px_-15px_rgba(0,0,0,0.05)]
- **Typography:** Geist/Satoshi, tracking-tight
- **Labels:** Outside and below cards (gallery style)
- **Padding:** p-8 or p-10 inside cards

### Perpetual Motion
- Every card needs micro-interaction (pulse, float, carousel)
- Use layout/layoutId for smooth re-ordering
- Memoize infinite animations in isolated Client Components

## Quality Checklist

- [ ] Mobile fallback (w-full, px-4) for asymmetric layouts
- [ ] min-h-[100dvh] for full-height sections
- [ ] Empty/loading/error states provided
- [ ] Cards omitted in favor of spacing where possible
- [ ] Hardware acceleration (transform/opacity only)
- [ ] Spring physics, no linear easing