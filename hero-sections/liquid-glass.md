# Liquid Glass Effect

## Core CSS

```css
.liquid-glass {
  background: rgba(255, 255, 255, 0.01);
  background-blend-mode: luminosity;
  backdrop-filter: blur(4px);
  -webkit-backdrop-filter: blur(4px);
  border: none;
  box-shadow: inset 0 1px 1px rgba(255, 255, 255, 0.1);
  position: relative;
  overflow: hidden;
}

.liquid-glass::before {
  content: '';
  position: absolute;
  inset: 0;
  border-radius: inherit;
  padding: 1.4px;
  background: linear-gradient(180deg,
    rgba(255,255,255,0.45) 0%,
    rgba(255,255,255,0.15) 20%,
    rgba(255,255,255,0) 40%,
    rgba(255,255,255,0) 60%,
    rgba(255,255,255,0.15) 80%,
    rgba(255,255,255,0.45) 100%
  );
  -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
  -webkit-mask-composite: xor;
  mask-composite: exclude;
  pointer-events: none;
}
```

## Usage in Components

### Navbar Pill
```tsx
<nav className="liquid-glass rounded-full px-6 py-3">
  <Logo />
  <NavLinks />
  <CTA />
</nav>
```

### Button
```tsx
<button className="liquid-glass rounded-full px-6 py-3">
  Get Started
</button>
```

### Badge
```tsx
<span className="liquid-glass rounded-full px-4 py-2 text-sm">
  New Feature
</span>
```

### Card
```tsx
<div className="liquid-glass rounded-3xl p-6">
  Content
</div>
```

## Stronger Variant

```css
.liquid-glass-strong {
  background: rgba(255, 255, 255, 0.01);
  background-blend-mode: luminosity;
  backdrop-filter: blur(50px);
  -webkit-backdrop-filter: blur(50px);
  border: none;
  box-shadow: 4px 4px 4px rgba(0, 0, 0, 0.05),
    inset 0 1px 1px rgba(255, 255, 255, 0.15);
}

.liquid-glass-strong::before {
  background: linear-gradient(180deg,
    rgba(255,255,255,0.5) 0%,
    rgba(255,255,255,0.2) 20%,
    rgba(255,255,255,0) 40%,
    rgba(255,255,255,0) 60%,
    rgba(255,255,255,0.2) 80%,
    rgba(255,255,255,0.5) 100%
  );
}
```

## Tailwind Plugin

```ts
// tailwind.config.ts
export default {
  theme: {
    extend: {
      backgroundImage: {
        'glass-gradient': 'linear-gradient(180deg, rgba(255,255,255,0.45) 0%, rgba(255,255,255,0.15) 20%, rgba(255,255,255,0) 40%, rgba(255,255,255,0) 60%, rgba(255,255,255,0.15) 80%, rgba(255,255,255,0.45) 100%)',
      },
    },
  },
};
```

## Browser Support

- `backdrop-filter` requires -webkit- prefix for Safari
- Test in iOS Safari for mobile behavior
- Consider fallback for older browsers

## Animation on Hover

```tsx
<button className="liquid-glass rounded-full px-6 py-3 hover:scale-[1.03] transition-transform">
  Button
</button>
```

## Dark Background Variant

For dark backgrounds, adjust the inner glow:

```css
.liquid-glass-dark {
  background: rgba(0, 0, 0, 0.4);
  /* Inner glow adjusted for dark backgrounds */
}
```