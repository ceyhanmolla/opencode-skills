---
name: web-page-design
description: Use when building premium landing pages with video backgrounds, glassmorphic effects, and cinematic animations
license: MIT
compatibility: opencode
metadata:
  audience: frontend-developers
  tech_stack: react,typescript,vite,tailwindcss,gsap,framer-motion
---

# Web Page Design

Build modern, high-performance web pages with premium visual effects.

## Tech Stack

- React 19+ with TypeScript
- Vite 6+ (build)
- Tailwind CSS v4 (@tailwindcss/vite)
- GSAP (menu, scroll triggers)
- Framer Motion (animations)
- lucide-react (icons)
- hls.js (video streaming)

## When to Use

- Premium landing pages with video backgrounds
- Glassmorphic UI effects
- Scroll-triggered animations
- Cinematic page transitions

## Color System

### CSS Variables
```css
:root {
  --background: 222 47% 11%;
  --foreground: 220 100% 97%;
  --surface: 0 0% 8%;
  --muted: 0 0% 53%;
  --stroke: 0 0% 12%;
  --accent: 84 100% 50%;
}
```

### Tailwind Config
```ts
colors: {
  background: 'hsl(var(--background))',
  foreground: 'hsl(var(--foreground))',
  surface: 'hsl(var(--surface))',
  muted: 'hsl(var(--muted))',
  stroke: 'hsl(var(--stroke))',
  accent: 'hsl(var(--accent))',
}
```

## Typography

### Font Imports
```css
@import url('https://fonts.googleapis.com/css2?family=Instrument+Serif:ital@0;1;0;1&family=Inter:wght@400;500;600;700&display=swap');
```

### Font Variables
```css
:root {
  --font-display: 'Instrument Serif', serif;
  --font-body: 'Inter', sans-serif;
}
```

| Type | Font | Usage |
|------|------|-------|
| Display | Instrument Serif (italic) | Headings |
| Body | Inter | Paragraphs |
| Accent | Anton | Uppercase bold |

## Video Background

### Standard
```tsx
<video autoPlay loop muted playsInline className="absolute inset-0 w-full h-full object-cover">
  <source src={src} type="video/mp4" />
</video>
```

### With Fade Loop
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

### HLS
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

## Liquid Glass Effect

### CSS
```css
.liquid-glass {
  background: rgba(255,255,255,0.01);
  background-blend-mode: luminosity;
  backdrop-filter: blur(4px);
  -webkit-backdrop-filter: blur(4px);
  box-shadow: inset 0 1px 1px rgba(255,255,255,0.1);
}
.liquid-glass::before {
  content: '';
  position: absolute;
  inset: 0;
  border-radius: inherit;
  padding: 1.4px;
  background: linear-gradient(180deg, rgba(255,255,255,0.45) 0%, rgba(255,255,255,0.15) 20%, rgba(255,255,255,0) 40%, rgba(255,255,255,0.15) 80%, rgba(255,255,255,0.45) 100%);
  -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
  -webkit-mask-composite: xor;
  mask-composite: exclude;
  pointer-events: none;
}
```

### Usage
```tsx
// Nav pill: <nav className="liquid-glass rounded-full px-6 py-3">
// Card: <div className="liquid-glass rounded-3xl p-6">
// Button: <button className="liquid-glass rounded-full px-6 py-3">
```

## Animations

### GSAP Staggered Menu
```tsx
useEffect(() => {
  if (!menuRef.current) return;
  const action = isOpen ? 'fromTo' : 'to';
  gsap[action](menuRef.current.children, isOpen ? { yPercent: 140, rotate: 10 } : { yPercent: 0, rotate: 0 }, { ...{ yPercent: 0, rotate: 0, duration: 1, ease: 'power4.out', stagger: 0.1 }, duration: 0.8, ease: 'power3.in' });
}, [isOpen]);
```

### Framer Text Reveal
```tsx
<motion.h1
  initial={{ opacity: 0, y: 40 }}
  animate={{ opacity: 1, y: 0 }}
  transition={{ duration: 0.96, ease: [0.22, 1, 0.36, 1] }}
>
  Text
</motion.h1>
```

### Staggered Children
```tsx
<motion.div initial="hidden" animate="visible" variants={{ visible: { transition: { staggerChildren: 0.12 } } } }}>
  {items.map(item => (
    <motion.div key={item} variants={{ hidden: { opacity: 0, y: 40 }, visible: { opacity: 1, y: 0 } }}>
      {item}
    </motion.div>
  ))}
</motion.div>
```

### CSS Animations
```css
@keyframes fade-rise { from { opacity: 0; transform: translateY(24px); } to { opacity: 1; transform: translateY(0); } }
.animate-fade-rise { animation: fade-rise 0.8s ease-out both; }

@keyframes marquee { 0% { transform: translateX(0%); } 100% { transform: translateX(-50%); } }
.animate-marquee { animation: marquee 20s linear infinite; }

@keyframes scroll-down { 0% { transform: translateY(-100%); } 50% { transform: translateY(200%); } 100% { transform: translateY(-100%); } }
.animate-scroll-down { animation: scroll-down 1.5s ease-in-out infinite; }
```

## Components

### Navbar
```tsx
const Navbar = () => {
  const [scrolled, setScrolled] = useState(false);
  useEffect(() => window.addEventListener('scroll', () => setScrolled(window.scrollY > 100)), []);
  return (
    <nav className={`fixed top-0 w-full z-50 flex justify-center pt-4 md:pt-6 px-4 ${scrolled ? 'shadow-md' : ''}`}>
      <div className="inline-flex items-center rounded-full backdrop-blur-md border border-white/10 bg-surface px-2 py-2">
        <div className="w-9 h-9 rounded-full border-2 border-accent flex items-center justify-center">
          <span className="font-display italic text-sm">Logo</span>
        </div>
        {['Home', 'Work', 'About'].map(item => (
          <button key={item} className="text-xs sm:text-sm rounded-full px-3 sm:px-4 py-1.5 sm:py-2 text-muted hover:text-foreground">{item}</button>
        ))}
        <button className="text-xs sm:text-sm rounded-full px-3 sm:px-4 py-1.5 sm:py-2 bg-stroke text-foreground">Contact</button>
      </div>
    </nav>
  );
};
```

### Hero
```tsx
<section className="relative h-screen overflow-hidden">
  <VideoBackground src={src} />
  <div className="relative z-10 flex flex-col items-center justify-center h-full px-6">
    <p className="text-xs text-muted uppercase tracking-[0.3em] mb-8">COLLECTION '26</p>
    <h1 className="text-6xl md:text-8xl lg:text-9xl font-display italic leading-[0.9] text-foreground mb-6">Heading</h1>
    <p className="text-sm text-muted max-w-md mb-12">Description</p>
    <div className="flex gap-4">
      <button className="rounded-full px-7 py-3.5 bg-foreground text-bg hover:scale-105">Primary</button>
      <button className="rounded-full px-7 py-3.5 border-2 border-stroke bg-bg">Secondary</button>
    </div>
  </div>
  <div className="absolute bottom-8 left-1/2 -translate-x-1/2">
    <span className="text-xs text-muted uppercase tracking-[0.2em]">SCROLL</span>
    <div className="w-px h-10 bg-stroke animate-scroll-down" />
  </div>
</section>
```

### Card Grid
```tsx
<div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
  {items.map((item, i) => (
    <motion.div key={item.id} initial={{ opacity: 0, y: 50 }} whileInView={{ opacity: 1, y: 0 }} viewport={{ once: true }} transition={{ duration: 0.8, delay: i * 0.15 }} className="liquid-glass rounded-3xl overflow-hidden group">
      <div className="aspect-video overflow-hidden">
        <img src={item.image} alt={item.title} className="w-full h-full object-cover group-hover:scale-105 transition-transform duration-700" />
      </div>
      <div className="p-6">
        <span className="text-xs uppercase tracking-widest text-muted mb-2 block">{item.category}</span>
        <h3 className="text-xl font-semibold text-foreground mb-2">{item.title}</h3>
        <p className="text-sm text-muted">{item.description}</p>
      </div>
    </motion.div>
  ))}
</div>
```

### Marquee
```tsx
<div className="overflow-hidden">
  <div className="flex animate-marquee">
    {[...items, ...items].map((item, i) => <div key={i} className="flex-shrink-0 px-8">{item}</div>)}
  </div>
</div>
```

## Responsive

| Breakpoint | Width |
|-----------|-------|
| sm | 640px |
| md | 768px |
| lg | 1024px |
| xl | 1280px |
| 2xl | 1536px |

```tsx
// Mobile-first
<div className="flex flex-col md:flex-row gap-6">
// Responsive type
<h1 className="text-4xl md:text-6xl lg:text-8xl">
// Hide/show
<div className="hidden md:block">
```

## Performance

- Use `transform` and `opacity` only for animations
- Use `playsInline` for mobile video
- Use HLS for streaming
- Respect `prefers-reduced-motion`
- Batch animations with `gsap.context()`

## Common Issues

| Issue | Fix |
|-------|-----|
| Video not playing | Add autoPlay, muted, playsInline |
| Animation lag | Use transform, not layout props |
| Glass not working | Add -webkit-backdrop-filter |
| Layout breaks | Mobile-first, test all breakpoints |

## Project Structure

```
src/
├── components/ui/       # Reusable UI
├── components/layout/    # Navbar, Footer
├── components/sections/ # Page sections
├── hooks/              # Custom hooks
├── styles/index.css   # Global styles
└── types/             # TypeScript types
```