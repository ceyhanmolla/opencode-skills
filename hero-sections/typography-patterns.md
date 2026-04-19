# Typography Patterns

## Font Imports

### Google Fonts
```css
@import url('https://fonts.googleapis.com/css2?family=Instrument+Serif:ital@0;1&family=Inter:wght@400;500;600;700&display=swap');
```

### Custom CSS Variables
```css
:root {
  --font-display: 'Instrument Serif', serif;
  --font-body: 'Inter', sans-serif;
}
```

## Font Pairings

### Display + Body
| Display Font | Body Font |
|--------------|----------|
| Instrument Serif | Inter |
| Anton | Inter |
| Geist | Geist Sans |
| Almarai | Inter |
| Manrope | Inter |
| General Sans | Inter |

### Premium Combinations
| Display | Body | Use Case |
|---------|------|---------|
| Instrument Serif (italic) | Inter | Creative/agencies |
| General Sans | Inter | SaaS/tech |
| Anton | Inter | Bold/impact |
| Almarai | Inter | Editorial |

## Typography Scale

### Headings
```tsx
// Mobile to Desktop
<h1 className="text-5xl md:text-7xl lg:text-8xl">
```

### Responsive Scale Table
| Element | Mobile | Tablet | Desktop |
|---------|--------|--------|--------|
| H1 | text-5xl | text-7xl | text-8xl |
| H2 | text-4xl | text-5xl | text-6xl |
| Subtext | text-base | text-lg | text-xl |
| Badge | text-xs | text-sm | text-sm |

## Style Patterns

### Cinematic Heading
```tsx
<h1 className="text-6xl md:text-8xl leading-[0.95] tracking-[-2px] font-normal">
  Where dreams rise <em className="not-italic text-muted">through silence</em>
</h1>
```

### Gradient Text
```tsx
<h1 className="bg-clip-text text-transparent bg-gradient-to-r from-white via-gray-400 to-gray-600">
  Heading Text
</h1>
```

### Italic Accent
```tsx
<p>Your vision <em className="not-italic font-serif italic">our reality</em></p>
```

## Tracking & Leading

| Style | CSS |
|-------|-----|
| Tight | tracking-tight leading-[0.95] |
| Normal | tracking-normal leading-normal |
| Loose | tracking-wide leading-relaxed |

## Font Weights

| Weight | Value | Use |
|--------|-------|-----|
| Light | 300 | Large decorative text |
| Normal | 400 | Body text |
| Medium | 500 | Emphasis |
| Semibold | 600 | Headings |
| Bold | 700 | CTA buttons |

## Implementation

### Inline Style
```tsx
<h1 style={{ fontFamily: "'Instrument Serif', serif" }}>
```

### Tailwind Config
```ts
// tailwind.config.ts
export default {
  theme: {
    extend: {
      fontFamily: {
        display: ["'Instrument Serif'", 'serif'],
        sans: ['Inter', 'sans-serif'],
      },
    },
  },
};
```

### Usage
```tsx
<h1 className="font-display italic">Heading</h1>
<p className="font-sans">Body</p>
```

## Best Practices

- Use consistent font pairing across site
- Limit to 2 font families maximum
- Use weight variations within same family
- Test readability at all sizes