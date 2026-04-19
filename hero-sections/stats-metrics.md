# Stats / Metrics Sections

## Basic 3-4 Column Stats

```tsx
<section className="bg-background py-20 px-6">
  <div className="max-w-6xl mx-auto">
    <div className="grid grid-cols-2 md:grid-cols-4 gap-8 text-center">
      {stats.map((stat, i) => (
        <motion.div
          key={i}
          initial={{ opacity: 0, y: 20 }}
          whileInView={{ opacity: 1, y: 0 }}
          viewport={{ once: true }}
          transition={{ delay: i * 0.1 }}
        >
          <p className="text-4xl md:text-5xl font-display">{stat.value}</p>
          <p className="text-sm text-muted mt-2">{stat.label}</p>
        </motion.div>
      ))}
    </div>
  </div>
</section>
```

## With Counter Animation

```tsx
import { useEffect, useState } from 'react';

const Counter = ({ end, duration = 2000 }) => {
  const [count, setCount] = useState(0);

  useEffect(() => {
    let start = 0;
    const increment = end / (duration / 16);
    const timer = setInterval(() => {
      start += increment;
      if (start >= end) {
        setCount(end);
        clearInterval(timer);
      } else {
        setCount(Math.floor(start));
      }
    }, 16);
    return () => clearInterval(timer);
  }, [end, duration]);

  return <span>{count.toLocaleString()}</span>;
};

// Usage
<Counter end={500} />+
<Counter end={98} />%
```

## Video Background with Stats Card

```tsx
<section className="relative py-20 overflow-hidden">
  <video autoPlay loop muted playsInline className="absolute inset-0 w-full h-full object-cover filter saturate-0">
    <source src={VIDEO_URL} type="video/mp4" />
  </video>
  <div className="absolute inset-0 bg-black/60" />
  <div className="relative z-10 max-w-4xl mx-auto px-6">
    <div className="liquid-glass rounded-3xl p-12 md:p-16">
      <div className="grid grid-cols-2 md:grid-cols-4 gap-8 text-center">
        {stats.map((stat, i) => (
          <div key={i}>
            <p className="text-4xl md:text-5xl font-display">{stat.value}</p>
            <p className="text-sm text-muted mt-2">{stat.label}</p>
          </div>
        ))}
      </div>
    </div>
  </div>
</section>
```

## Big Numbers with Labels

```tsx
<div className="text-center">
  <p className="text-6xl md:text-8xl font-display">200+</p>
  <p className="text-lg text-muted mt-4">Projects Launched</p>
</div>
```

## Progress Bar Stats

```tsx
<div className="space-y-6">
  {metrics.map((m, i) => (
    <div key={i}>
      <div className="flex justify-between mb-2">
        <span>{m.label}</span>
        <span>{m.value}%</span>
      </div>
      <div className="h-2 bg-surface rounded-full overflow-hidden">
        <motion.div
          initial={{ width: 0 }}
          whileInView={{ width: `${m.value}%` }}
          viewport={{ once: true }}
          transition={{ duration: 1, delay: i * 0.2 }}
          className="h-full bg-accent"
        />
      </div>
    </div>
  ))}
</div>
```

## Animated Number with Prefix/Suffix

```tsx
<motion.div>
  <span className="text-5xl font-display">
    <Counter end={value} />
  </span>
  <span className="text-2xl">{suffix}</span> {/* e.g., +%, +, $ */}
</motion.div>
```

## Stats with Icons

```tsx
<div className="flex items-center gap-4">
  <div className="liquid-glass-strong rounded-full w-12 h-12 flex items-center justify-center">
    <Zap className="w-6 h-6" />
  </div>
  <div>
    <p className="text-2xl font-semibold">48h</p>
    <p className="text-sm text-muted">Average delivery</p>
  </div>
</div>
```

## Grid with Descriptions

```tsx
<div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
  {stats.map((stat, i) => (
    <div key={i} className="text-center">
      <p className="text-5xl font-display italic">{stat.value}</p>
      <p className="font-medium mt-2">{stat.label}</p>
      <p className="text-sm text-muted mt-1">{stat.description}</p>
    </div>
  ))}
</div>
```

## Horizontal Scroll Stats

```tsx
<div className="flex gap-16 overflow-x-auto pb-4">
  {stats.map((stat, i) => (
    <div key={i} className="flex-shrink-0 text-center">
      <p className="text-4xl font-display">{stat.value}</p>
      <p className="text-sm text-muted">{stat.label}</p>
    </div>
  ))}
</div>
```

## Gradient Accent Stats

```tsx
<p className="text-5xl font-display bg-clip-text text-transparent bg-gradient-to-r from-accent to-accent/50">
  98%
</p>
```