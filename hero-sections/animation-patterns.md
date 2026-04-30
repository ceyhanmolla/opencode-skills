# Animation Patterns

## CSS Keyframes

### Fade Rise
```css
@keyframes fade-rise {
  from { opacity: 0; transform: translateY(24px); }
  to { opacity: 1; transform: translateY(0); }
}
.animate-fade-rise { animation: fade-rise 0.8s ease-out both; }
.animate-fade-rise-delay { animation: fade-rise 0.8s ease-out 0.2s both; }
.animate-fade-rise-delay-2 { animation: fade-rise 0.8s ease-out 0.4s both; }
```

### Scroll Down
```css
@keyframes scroll-down {
  0% { transform: translateY(-100%); }
  50% { transform: translateY(200%); }
  100% { transform: translateY(-100%); }
}
.animate-scroll-down { animation: scroll-down 1.5s ease-in-out infinite; }
```

### Marquee
```css
@keyframes marquee {
  0% { transform: translateX(0%); }
  100% { transform: translateX(-50%); }
}
.animate-marquee { animation: marquee 20s linear infinite; }
```

## Framer Motion

### Text Reveal
```tsx
import { motion } from 'framer-motion';

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
<motion.div
  initial="hidden"
  animate="visible"
  variants={{
    visible: { transition: { staggerChildren: 0.12 } },
  }}
>
  {items.map((item) => (
    <motion.div
      key={item}
      variants={{
        hidden: { opacity: 0, y: 40 },
        visible: { opacity: 1, y: 0 },
      }}
    >
      {item}
    </motion.div>
  ))}
</motion.div>
```

### Blur Text
```tsx
const BlurText = ({ text }: { text: string }) => {
  return text.split(' ').map((word, i) => (
    <motion.span
      key={i}
      initial={{ filter: 'blur(10px)', opacity: 0 }}
      whileInView={{ filter: 'blur(0px)', opacity: 1 }}
      viewport={{ once: true }}
      transition={{ duration: 0.5, delay: i * 0.1 }}
    >
      {word}{' '}
    </motion.span>
  ));
};
```

## GSAP

### Staggered Menu
```tsx
import { gsap } from 'gsap';

useEffect(() => {
  if (!menuRef.current) return;
  if (isOpen) {
    gsap.fromTo(
      menuRef.current.children,
      { yPercent: 140, rotate: 10 },
      { yPercent: 0, rotate: 0, duration: 1, ease: 'power4.out', stagger: 0.1 }
    );
  }
}, [isOpen]);
```

### ScrollTrigger Parallax
```tsx
import { ScrollTrigger } from 'gsap/ScrollTrigger';
gsap.registerPlugin(ScrollTrigger);

useEffect(() => {
  gsap.to(parallaxRef.current, {
    yPercent: -50,
    ease: 'none',
    scrollTrigger: {
      trigger: sectionRef.current,
      start: 'top bottom',
      end: 'bottom top',
      scrub: true,
    },
  });
}, []);
```

## Staggered Animation Table

| Delay | Element |
|-------|---------|
| 0s | H1 Heading |
| 0.2s | Subtext |
| 0.4s | CTA Button |
| 0.6s | Secondary elements |

## UseInView Animation

```tsx
import { useInView } from 'framer-motion';

const Section = () => {
  const ref = useRef(null);
  const isInView = useInView(ref, { once: true, margin: '-100px' });

  return (
    <motion.div
      ref={ref}
      initial={{ opacity: 0, y: 50 }}
      animate={isInView ? { opacity: 1, y: 0 } : {}}
      transition={{ duration: 0.8 }}
    />
  );
};
```

## Spring Physics

```tsx
<motion.button
  whileHover={{ scale: 1.05 }}
  whileTap={{ scale: 0.95 }}
  transition={{ type: 'spring', stiffness: 100, damping: 20 }}
>
```

## Reduced Motion

```css
@media (prefers-reduced-motion: reduce) {
  * {
    animation: none !important;
    transition: none !important;
  }
}
```

## Performance Tips

- Animate only `transform` and `opacity`
- Avoid `layout` properties
- Use `will-change` sparingly
- Memoize infinite loops