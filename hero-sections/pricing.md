# Pricing Sections

## Two Cards (Dark + Light)

```tsx
<section className="bg-background py-20 px-6">
  <div className="max-w-4xl mx-auto grid grid-cols-1 md:grid-cols-2 gap-8">
    {/* Dark Card */}
    <div className="bg-foreground text-background rounded-[40px] p-10">
      <h3 className="text-xl font-medium">Monthly Partnership</h3>
      <p className="text-sm opacity-80 mt-2">A dedicated creative team.</p>
      <p className="text-3xl font-display mt-6">$5,000<span className="text-lg opacity-80">/mo</span></p>
      <button className="mt-8 w-full bg-background text-foreground rounded-full py-4 font-medium">
        Start a chat
      </button>
    </div>

    {/* Light Card */}
    <div className="liquid-glass rounded-[40px] p-10">
      <h3 className="text-xl font-medium">Custom Project</h3>
      <p className="text-sm text-muted mt-2">Fixed scope, fixed timeline.</p>
      <p className="text-3xl font-display mt-6">$5,000<span className="text-sm text-muted"> min</span></p>
      <button className="mt-8 w-full liquid-glass rounded-full py-4 font-medium">
        Start a chat
      </button>
    </div>
  </div>
</section>
```

## Three Tier Cards

```tsx
<section className="py-20 px-6">
  <div className="max-w-6xl mx-auto grid grid-cols-1 md:grid-cols-3 gap-6">
    {plans.map((plan, i) => (
      <motion.div
        key={i}
        initial={{ opacity: 0, y: 30 }}
        whileInView={{ opacity: 1, y: 0 }}
        viewport={{ once: true }}
        transition={{ delay: i * 0.1 }}
        className={`liquid-glass rounded-3xl p-8 ${plan.popular ? 'border-accent border-2' : ''}`}
      >
        {plan.popular && (
          <span className="text-xs bg-accent text-accent-foreground px-2 py-1 rounded-full">Popular</span>
        )}
        <h3 className="text-xl font-semibold mt-4">{plan.name}</h3>
        <p className="text-3xl font-display mt-4">${plan.price}<span className="text-sm text-muted">/mo</span></p>
        <ul className="mt-6 space-y-3">
          {plan.features.map((f, j) => (
            <li key={j} className="flex items-center gap-2">
              <Check className="w-4 h-4" /> {f}
            </li>
          ))}
        </ul>
        <button className={`mt-8 w-full rounded-full py-3 ${plan.popular ? 'bg-accent' : 'liquid-glass'}`}>
          Get Started
        </button>
      </motion.div>
    ))}
  </div>
</section>
```

## Toggle (Monthly/Yearly)

```tsx
const [annual, setAnnual] = useState(false);

<div className="flex items-center justify-center gap-4 mb-12">
  <span className={!annual ? 'font-medium' : 'text-muted'}>Monthly</span>
  <button
    onClick={() => setAnnual(!annual)}
    className="w-14 h-8 bg-surface rounded-full relative"
  >
    <motion.div
      className="w-6 h-6 bg-accent rounded-full absolute top-1"
      animate={{ x: annual ? 28 : 4 }}
    />
  </button>
  <span className={annual ? 'font-medium' : 'text-muted'}>Yearly</span>
  {annual && <span className="text-xs text-accent rounded-full px-2 py-1">-20%</span>}
</div>
```

## Pricing Table

```tsx
<div className="liquid-glass rounded-3xl overflow-hidden">
  <table className="w-full">
    <thead>
      <tr className="border-b border-surface">
        <th className="text-left p-4">Feature</th>
        <th className="text-center p-4">Basic</th>
        <th className="text-center p-4">Pro</th>
        <th className="text-center p-4">Enterprise</th>
      </tr>
    </thead>
    <tbody>
      {features.map((f, i) => (
        <tr key={i} className="border-b border-surface/50">
          <td className="p-4">{f.name}</td>
          <td className="text-center p-4">{f.basic ? <Check /> : <X />}</td>
          <td className="text-center p-4">{f.pro ? <Check /> : <X />}</td>
          <td className="text-center p-4">{f.enterprise ? <Check /> : <X />}</td>
        </tr>
      ))}
    </tbody>
  </table>
</div>
```

## Comparison Highlight

```tsx
<div className="grid grid-cols-3 gap-4 text-center">
  <div className="p-4">
    <p className="text-2xl font-display">$0</p>
    <p className="text-sm text-muted">Free</p>
  </div>
  <div className="p-4 bg-accent/10 rounded-2xl">
    <p className="text-2xl font-display">$29</p>
    <p className="text-sm text-muted">Pro</p>
  </div>
  <div className="p-4">
    <p className="text-2xl font-display">$99</p>
    <p className="text-sm text-muted">Business</p>
  </div>
</div>
```

## FAQ Accordion

```tsx
import { useState } from 'react';

const FAQ = ({ items }) => {
  const [open, setOpen] = useState(null);

  return (
    <div className="max-w-2xl mx-auto">
      {items.map((item, i) => (
        <div key={i} className="border-b border-surface">
          <button
            onClick={() => setOpen(open === i ? null : i)}
            className="w-full flex justify-between items-center p-4 text-left"
          >
            <span className="font-medium">{item.question}</span>
            <motion.span animate={{ rotate: open === i ? 180 : 0 }}>
              <ChevronDown className="w-5 h-5" />
            </motion.span>
          </button>
          <motion.div
            initial={false}
            animate={{ height: open === i ? 'auto' : 0, opacity: open === i ? 1 : 0 }}
            className="overflow-hidden"
          >
            <p className="p-4 text-muted">{item.answer}</p>
          </motion.div>
        </div>
      ))}
    </div>
  );
};
```

## CTA in Pricing

```tsx
<div className="text-center mt-12">
  <p className="text-muted mb-4">Need a custom plan?</p>
  <button className="liquid-glass rounded-full px-8 py-3">
    Contact Sales
  </button>
</div>
```