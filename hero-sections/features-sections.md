# Features Sections

## Grid Layout (3-4 columns)

```tsx
<section className="bg-background py-20 px-6">
  <div className="max-w-6xl mx-auto">
    <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
      {features.map((feature, i) => (
        <motion.div
          key={feature.title}
          initial={{ opacity: 0, y: 50 }}
          whileInView={{ opacity: 1, y: 0 }}
          viewport={{ once: true }}
          transition={{ delay: i * 0.15, duration: 0.8 }}
          className="liquid-glass rounded-3xl p-6"
        >
          <Icon className="w-10 h-10 text-accent mb-4" />
          <h3 className="text-xl font-semibold mb-2">{feature.title}</h3>
          <p className="text-muted">{feature.description}</p>
        </motion.div>
      ))}
    </div>
  </div>
</section>
```

## Alternating (Chess Pattern)

```tsx
<section className="bg-background py-20 px-6">
  {features.map((feature, i) => (
    <div key={i} className={`flex flex-col md:flex-row gap-12 mb-20 ${i % 2 === 1 ? 'md:flex-row-reverse' : ''}`}>
      <div className="flex-1">
        <h3 className="text-3xl font-display mb-4">{feature.title}</h3>
        <p className="text-lg text-muted">{feature.description}</p>
      </div>
      <div className="flex-1 liquid-glass rounded-3xl overflow-hidden">
        <img src={feature.image} alt={feature.title} className="w-full h-full object-cover" />
      </div>
    </div>
  ))}
</section>
```

## Bento Grid

```tsx
<section className="bg-background py-20 px-6">
  <div className="grid grid-cols-1 md:grid-cols-4 gap-4">
    {/* Large card - spans 2 columns */}
    <motion.div className="md:col-span-2 md:row-span-2 liquid-glass rounded-3xl p-8">
      <h3 className="text-2xl font-display">{features[0].title}</h3>
      <p className="text-muted mt-4">{features[0].description}</p>
    </motion.div>

    {/* Small cards */}
    {features.slice(1, 5).map((f, i) => (
      <motion.div key={i} className="liquid-glass rounded-3xl p-6">
        <Icon />
        <h4 className="font-semibold">{f.title}</h4>
      </motion.div>
    ))}
  </div>
</section>
```

## With Video Background

```tsx
<section className="relative py-20 overflow-hidden">
  <video autoPlay loop muted playsInline className="absolute inset-0 w-full h-full object-cover">
    <source src="VIDEO_URL" type="video/mp4" />
  </video>
  <div className="absolute inset-0 bg-black/60" />
  <div className="relative z-10 max-w-6xl mx-auto px-6">
    <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
      {features.map(f => (
        <div className="liquid-glass rounded-3xl p-6">
          <h3 className="text-xl font-semibold">{f.title}</h3>
          <p className="text-muted">{f.description}</p>
        </div>
      ))}
    </div>
  </div>
</section>
```

## Cards with Hover Effect

```tsx
<motion.div
  whileHover={{ scale: 1.02 }}
  className="liquid-glass rounded-3xl overflow-hidden group"
>
  <div className="aspect-video overflow-hidden">
    <img
      src={feature.image}
      alt={feature.title}
      className="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105"
    />
  </div>
  <div className="p-6">
    <span className="text-xs uppercase tracking-widest text-accent">{feature.tag}</span>
    <h3 className="text-xl font-semibold mt-2">{feature.title}</h3>
    <p className="text-muted mt-2">{feature.description}</p>
  </div>
</motion.div>
```

## Icon + Title + Description

```tsx
<div className="liquid-glass rounded-2xl p-6">
  <div className="liquid-glass-strong rounded-full w-12 h-12 flex items-center justify-center mb-4">
    <Zap className="w-6 h-6" />
  </div>
  <h4 className="text-lg font-semibold">{title}</h4>
  <p className="text-sm text-muted mt-2">{description}</p>
</div>
```

## Badge + Heading + Grid

```tsx
<section className="bg-background py-24">
  <div className="max-w-6xl mx-auto px-6">
    <span className="liquid-glass rounded-full px-4 py-1 text-sm">Label</span>
    <h2 className="text-4xl font-display mt-6 mb-12">Section Title</h2>

    <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
      {items.map((item, i) => (
        <FeatureCard key={i} {...item} />
      ))}
    </div>
  </div>
</section>
```

## Scroll-triggered with useInView

```tsx
import { useInView } from 'framer-motion';

const FeatureSection = () => {
  const ref = useRef(null);
  const isInView = useInView(ref, { once: true, margin: '-100px' });

  return (
    <div ref={ref} className="grid grid-cols-3 gap-6">
      {features.map((f, i) => (
        <motion.div
          key={i}
          initial={{ opacity: 0, y: 50 }}
          animate={isInView ? { opacity: 1, y: 0 } : {}}
          transition={{ delay: i * 0.1, duration: 0.6 }}
        >
          <FeatureCard {...f} />
        </motion.div>
      ))}
    </div>
  );
};
```