# Testimonials

## Basic Card Grid (3 columns)

```tsx
<section className="bg-background py-20 px-6">
  <div className="max-w-6xl mx-auto">
    <h2 className="text-4xl font-display text-center mb-12">What they say</h2>
    <div className="grid grid-cols-1 md:grid-cols-3 gap-6">
      {testimonials.map((t, i) => (
        <motion.div
          key={i}
          initial={{ opacity: 0, y: 30 }}
          whileInView={{ opacity: 1, y: 0 }}
          viewport={{ once: true }}
          transition={{ delay: i * 0.1 }}
          className="liquid-glass rounded-2xl p-8"
        >
          <Quote className="w-8 h-8 text-muted mb-4" />
          <p className="text-lg mb-6">{t.quote}</p>
          <div className="flex items-center gap-4">
            <img src={t.avatar} alt={t.name} className="w-12 h-12 rounded-full" />
            <div>
              <p className="font-semibold">{t.name}</p>
              <p className="text-sm text-muted">{t.role}</p>
            </div>
          </div>
        </motion.div>
      ))}
    </div>
  </div>
</section>
```

## Auto-scrolling Carousel

```tsx
const Carousel = ({ testimonials }) => {
  const [current, setCurrent] = useState(0);

  useEffect(() => {
    const interval = setInterval(() => {
      setCurrent(c => (c + 1) % testimonials.length);
    }, 3000);
    return () => clearInterval(interval);
  }, [testimonials.length]);

  return (
    <div className="relative max-w-4xl mx-auto px-6">
      <motion.div
        key={current}
        initial={{ opacity: 0, scale: 0.95 }}
        animate={{ opacity: 1, scale: 1 }}
        exit={{ opacity: 0 }}
        className="liquid-glass rounded-3xl p-12 text-center"
      >
        <Quote className="w-12 h-12 mx-auto mb-6" />
        <p className="text-2xl font-display mb-8">"{testimonials[current].quote}"</p>
        <div className="flex items-center justify-center gap-4">
          <img src={testimonials[current].avatar} className="w-14 h-14 rounded-full" />
          <div className="text-left">
            <p className="font-semibold">{testimonials[current].name}</p>
            <p className="text-sm text-muted">{testimonials[current].role}</p>
          </div>
        </div>
      </motion.div>

      {/* Dots */}
      <div className="flex justify-center gap-2 mt-6">
        {testimonials.map((_, i) => (
          <button
            key={i}
            onClick={() => setCurrent(i)}
            className={`w-2 h-2 rounded-full transition ${i === current ? 'bg-foreground' : 'bg-muted/30'}`}
          />
        ))}
      </div>
    </div>
  );
};
```

## Scroll-driven Word Reveal

```tsx
import { useScroll, useTransform } from 'framer-motion';

const WordReveal = ({ text }: { text: string }) => {
  const ref = useRef(null);
  const { scrollYProgress } = useScroll({
    target: ref,
    offset: ['start end', 'end center']
  });

  const words = text.split(' ');

  return (
    <div ref={ref} className="flex flex-wrap justify-center">
      {words.map((word, i) => {
        const start = i / words.length;
        const end = (i + 1) / words.length;
        const opacity = useTransform(scrollYProgress, [start, end], [0.2, 1]);

        return (
          <motion.span
            key={i}
            style={{ opacity }}
            className="mr-[0.3em]"
          >
            {word}
          </motion.span>
        );
      })}
    </div>
  );
};

// Usage
<WordReveal text="This product revolutionized how we handle financial insights..." />
```

## Single Large Quote

```tsx
<section className="py-24 px-6">
  <div className="max-w-3xl mx-auto text-center">
    <Quote className="w-14 h-14 mx-auto mb-8 text-muted" />
    <h2 className="text-4xl md:text-5xl font-display leading-tight">
      <WordReveal text="CompanyName revolutionized how we handle financial insights using smart analytics. We are now driving better outcomes quicker than we ever imagined!" />
    </h2>
    <div className="flex items-center justify-center gap-4 mt-12">
      <img src={avatar} className="w-14 h-14 rounded-full border-2 border-foreground" />
      <div className="text-left">
        <p className="font-semibold">Author Name</p>
        <p className="text-sm text-muted">Role, Company</p>
      </div>
    </div>
  </div>
</section>
```

## Logo Cloud + Testimonial

```tsx
<section className="py-20">
  {/* Logo Cloud */}
  <div className="flex justify-center gap-8 mb-12 opacity-60">
    {logos.map((logo, i) => (
      <span key={i} className="text-2xl font-display">{logo}</span>
    ))}
  </div>

  {/* Testimonial */}
  <div className="max-w-2xl mx-auto px-6 text-center">
    <p className="text-xl italic">"{testimonial.quote}"</p>
    <p className="mt-4 font-medium">— {testimonial.name}</p>
  </div>
</section>
```

## Card with Rating Stars

```tsx
<div className="liquid-glass rounded-2xl p-6">
  <div className="flex gap-1 mb-4">
    {[...Array(5)].map((_, i) => (
      <Star key={i} className="w-4 h-4 fill-accent text-accent" />
    ))}
  </div>
  <p className="mb-4">"{quote}"</p>
  <div className="flex items-center gap-3">
    <img src={avatar} className="w-10 h-10 rounded-full" />
    <div>
      <p className="font-semibold text-sm">{name}</p>
      <p className="text-xs text-muted">{role}</p>
    </div>
  </div>
</div>
```

## Horizontal Scrolling Marquee

```tsx
const Marquee = ({ testimonials }) => {
  const duplicated = [...testimonials, ...testimonials];

  return (
    <div className="overflow-hidden py-12">
      <motion.div
        className="flex gap-6"
        animate={{ x: ['0%', '-50%'] }}
        transition={{ repeat: Infinity, duration: 20, ease: 'linear' }}
      >
        {duplicated.map((t, i) => (
          <div key={i} className="liquid-glass rounded-2xl p-6 min-w-[300px]">
            <p className="mb-4">"{t.quote}"</p>
            <p className="font-medium text-sm">— {t.name}</p>
          </div>
        ))}
      </motion.div>
    </div>
  );
};
```