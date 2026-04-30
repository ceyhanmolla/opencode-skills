---
name: aura-design-systems
description: Automatically selects from reference design files. Analyzes project brief, presents best-matching designs, and extracts all design tokens (colors, typography, spacing, rounded) from the selected design.
license: MIT
compatibility: opencode
metadata:
  audience: designers-developers
  use-case: design-token-generation
---

# Aura Design Systems Skill

Automatically selects the best-matching design from 160+ reference design files in the reference folder.

## Workflow

### 1. Collect Project Brief

Gather the following information from the user:
- **Project type**: SaaS dashboard, landing page, e-commerce, fintech, etc.
- **Industry/Sector**: Finance, healthcare, education, gaming, etc.
- **Tone/Style**: Minimal, bold, futuristic, elegant, playful, etc.
- **Color preference**: Company color or preferred palette if available
- **Key features**: Dark mode needed? Animations? WebGL effects?

Ask questions one at a time. If ambiguous, provide multiple choices.

### 2. Analyze Reference Designs

Scan all `-DESIGN.md` files in `~/.opencode/skills/aura-design-systems/reference/`.

Each design file has these fields in frontmatter:
```yaml
version: "neuform-pro"
name: "Design Name"
description: "Short description"
tags: dashboard, animated, webgl, charts, effect
colors:
  primary: "#..."
  secondary: "#..."
  accent: "#..."
  background: "#..."
  surface: "#..."
  text-primary: "#..."
  text-secondary: "#..."
  border: "#..."
typography:
  display-lg: { fontFamily, fontSize, fontWeight, lineHeight, letterSpacing }
  body-md: { fontFamily, fontSize, fontWeight, lineHeight, letterSpacing }
  label-md: { fontFamily, fontSize, fontWeight, lineHeight, letterSpacing }
spacing:
  base: "8px"
  gap: "16px"
  card-padding: "24px"
  section-padding: "80px"
rounded:
  card: "15px"
  control: "11px"
  pill: "9999px"
components:
  card: { background, radius }
  button: { background, radius }
```

Filter by tags:
- **Dashboard/Admin**: `dashboard`, `analytics`, `metrics`
- **Landing Page**: `landing`, `hero`, `feature`, `cta`
- **Finance/Payment**: `payment`, `financial`, `transaction`
- **Animated/WebGL**: `animated`, `webgl`, `effect`
- **Mobile**: `mobile`, `app`

### 3. Present Best 2-3 Matches

For each option, include:
- **Design name and source**
- **Why this design was chosen** (tag match, color proximity, style alignment)
- **Color palette preview**
- **Key features** (radius values, typography family)

Example presentation:
```
## Recommended Designs

### 1. Nexus Core (Recommended)
**Why**: Dashboard + metrics + dark mode match 90%
**Tags**: dashboard, animated, webgl

Colors:
- Primary: #09090B
- Background: #050505
- Surface: #E5E5E5

Radius: card 15px, control 11px

### 2. Aether Architects
**Why**: Similar dark palette, bento layout
**Tags**: footer, bento, cta

...
```

### 4. Get User Selection

Ask user to pick one or say "None of these work".

**If rejected**: Loosen criteria or try different angles.

### 5. Extract Token from Selected Design

After user approval, extract the frontmatter from the selected DESIGN.md file and present in this format:

```yaml
## Selected Design Tokens

### Colors
| Token | Hex | Usage |
|-------|-----|-------|
| primary | #09090B | Main buttons, accents |
| background | #050505 | Page background |
| surface | #E5E5E5 | Card surfaces |
| text-primary | #FFFFFF | Headings |
| text-secondary | #A1A1AA | Descriptions |
| border | #27272A | Borders |

### Typography
| Level | Font | Size | Weight |
|--------|------|------|--------|
| display-lg | Inter | 64px | 500 |
| body-md | Inter | 16px | 400 |
| label-md | JetBrains Mono | 12px | 600 |

### Spacing
- base: 8px
- gap: 16px
- card-padding: 24px
- section-padding: 80px

### Radius
- card: 15px
- control: 11px
- pill: 9999px
```

## Reference Folder Structure

```
aura-design-systems/
├── SKILL.md (this file)
└── reference/
    ├── nexus-core-DESIGN.md
    ├── aether-architects-DESIGN.md
    ├── aurora-gl-ethereal-DESIGN.md
    └── ... (160+ design files)
```

## Tag Reference

Tags used in reference designs:

| Tag | Description |
|-----|-------------|
| dashboard | Admin panel, analytics |
| landing | Landing page |
| hero | Hero section |
| feature | Feature showcase |
| bento | Bento grid layout |
| cta | Call to action |
| animated | Contains animations |
| webgl | WebGL/canvas effects |
| charts | Contains charts |
| metrics | Metric display |
| payment | Payment/billing |
| financial | Financial |
| mobile | Mobile compatible |
| footer | Footer section |
| navigation | Navigation |
| dark | Dark theme dominant |

## Important Rules

1. **Always give user choice** - Never auto-select, present and wait
2. **Explain your reasoning** - State why each design was chosen
3. **Extract complete tokens** - After approval, present all values
4. **Preserve guardrails** - Also transfer each DESIGN.md's "Guardrails" section (dos and don'ts)
5. **Color proximity** - If user provides company color, find closest matches using LAB color distance