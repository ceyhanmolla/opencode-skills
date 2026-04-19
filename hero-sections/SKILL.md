---
name: hero-sections
description: Use when building premium hero sections with video backgrounds, glassmorphic effects, cinematic animations, and high-end typography
license: MIT
compatibility: opencode
metadata:
  audience: frontend-developers
  skill_type: reference
  patterns: video-background,glass-effect,typography,animations
---

# Hero Sections

Premium hero section tasarımları için kapsamlı referans rehberi.

## Quick Reference

| Section | Dosya |
|---------|-------|
| Video Backgrounds | video-patterns.md |
| Typography | typography-patterns.md |
| Liquid Glass Effect | liquid-glass.md |
| Animations | animation-patterns.md |
| Color Themes | color-themes.md |
| Features Sections | features-sections.md |
| Testimonials | testimonials.md |
| Stats/Metrics | stats-metrics.md |
| Pricing | pricing.md |
| CTA/Footer | cta-footer.md |

## Page Sections

### Complete Landing Page Structure
```tsx
<div>
  {/* Navigation */}
  <Navbar />

  {/* Hero Section */}
  <HeroSection />

  {/* Features */}
  <Features />

  {/* How It Works / About */}
  <HowItWorks />

  {/* Stats */}
  <Stats />

  {/* Testimonials */}
  <Testimonials />

  {/* CTA */}
  <CTASection />

  {/* Footer */}
  <Footer />
</div>
```

## When to Use

Video barındıran full-screen hero section'lar için:
- Premium landing pages
- SaaS/product tanıtım sayfaları
- Agency/creative studio siteleri

## Required Technologies

- React 18+ / Next.js
- Tailwind CSS v3/v4
- TypeScript
- Optional: Framer Motion, GSAP, hls.js

## Essential Setup

### Tailwind Config
```ts
colors: {
  background: 'hsl(var(--background))',
  foreground: 'hsl(var(--foreground))',
  muted: 'hsl(var(--muted))',
}
```

### CSS Variables (index.css)
```css
:root {
  --background: 0 0% 3%;
  --foreground: 0 0% 100%;
  --muted: 0 0% 65%;
}
```

## Video Integration

### Basic Loop
```tsx
<video
  autoPlay
  loop
  muted
  playsInline
  className="absolute inset-0 w-full h-full object-cover"
>
  <source src="URL" type="video/mp4" />
</video>
```

### Fade Loop (Advanced)
```tsx
const videoRef = useRef<HTMLVideoElement>(null);
const [opacity, setOpacity] = useState(0);

useEffect(() => {
  const v = videoRef.current;
  if (!v) return;
  const fadeIn = () => {
    let o = 0;
    const anim = () => {
      o += 0.02;
      o >= 1 ? setOpacity(1) : (setOpacity(o), requestAnimationFrame(anim));
    };
    anim();
  };
  v.addEventListener('canplay', () => { v.play(); fadeIn(); });
  return () => v.removeEventListener('canplay', () => v.play());
}, []);

return <video ref={videoRef} autoPlay muted playsInline style={{ opacity }} className="absolute inset-0 object-cover" />;
```

### HLS Stream
```tsx
import Hls from 'hls.js';
const videoRef = useRef<HTMLVideoElement>(null);
useEffect(() => {
  const v = videoRef.current;
  if (Hls.isSupported() && v) new Hls().loadSource(src).attachMedia(v);
  else v && (v.src = src);
}, [src]);
return <video ref={videoRef} autoPlay loop muted playsInline className="absolute inset-0" />;
```

## Common Patterns

### Hero Structure (Full Viewport)
```tsx
<section className="relative h-screen overflow-hidden">
  {/* Video Background */}
  <video className="absolute inset-0 w-full h-full object-cover z-0">
    <source src="URL" type="video/mp4" />
  </video>

  {/* Overlay (optional) */}
  <div className="absolute inset-0 bg-black/50 z-0" />

  {/* Content */}
  <div className="relative z-10 flex flex-col items-center justify-center min-h-screen px-6">
    {/* Navbar, Hero Content, CTA */}
  </div>
</section>
```

### Navbar (Floating Glass)
```tsx
<nav className="fixed top-0 left-0 right-0 z-50 flex justify-center pt-4">
  <div className="liquid-glass rounded-full px-6 py-3 flex items-center gap-6">
    <Logo />
    <NavLinks />
    <CTA />
  </div>
</nav>
```

### Typography Scale
| Element | Mobile | Desktop |
|---------|--------|---------|
| H1 | text-5xl | text-8xl |
| Subtext | text-lg | text-xl |
| Badge | text-xs | text-sm |

## Animations

### CSS Keyframes
```css
@keyframes fade-rise {
  from { opacity: 0; transform: translateY(24px); }
  to { opacity: 1; transform: translateY(0); }
}
.animate-fade-rise { animation: fade-rise 0.8s ease-out both; }
.animate-fade-rise-delay { animation: fade-rise 0.8s ease-out 0.2s both; }
```

### Framer Motion
```tsx
<motion.h1
  initial={{ opacity: 0, y: 40 }}
  animate={{ opacity: 1, y: 0 }}
  transition={{ duration: 0.96, ease: [0.22, 1, 0.36, 1] }}
>
```

## Color Themes

### Dark Theme
```css
--background: 260 87% 3%;
--foreground: 40 6% 95%;
--muted: 40 6% 65%;
```

### Deep Navy
```css
--background: 201 100% 13%;
--foreground: 0 0% 100%;
```

### Premium Black
```css
--background: 0 0% 4%;
--foreground: 0 0% 96%;
```

## Font Systems

### Display + Body
```css
@import url('https://fonts.googleapis.com/css2?family=Instrument+Serif:ital@0;1&family=Inter:wght@400;500;600&display=swap');
:root {
  --font-display: 'Instrument Serif', serif;
  --font-body: 'Inter', sans-serif;
}
```

### Usage
```tsx
// Heading
<h1 style={{ fontFamily: "'Instrument Serif', serif" }}>

// Body
<p className="font-sans">
```

## Components

### Hero Badge
```tsx
<span className="liquid-glass rounded-full px-4 py-2 text-sm">
  <span className="bg-white text-black rounded-md px-2 py-0.5 mr-2">New</span>
  Feature text
</span>
```

### CTA Button
```tsx
<button className="liquid-glass rounded-full px-8 py-4 text-foreground hover:scale-105">
  Get Started
</button>
```

## Accessibility

- Use `playsInline` for mobile video autoplay
- Add `prefers-reduced-motion` media query for animations
- Ensure color contrast ratios for text over video
- Provide poster image as fallback

## File Structure
```
hero-sections/
├── SKILL.md              # Main reference
├── video-patterns.md     # Video patterns
├── typography-patterns.md  # Typography
├── liquid-glass.md      # Glass effect CSS
├── animation-patterns.md # Animations
└── color-themes.md     # Color systems
```