# CTA & Footer Sections

## Video Background CTA

```tsx
<section className="relative py-20 overflow-hidden">
  <video autoPlay loop muted playsInline className="absolute inset-0 w-full h-full object-cover">
    <source src="VIDEO_URL" type="video/mp4" />
  </video>
  <div className="absolute inset-0 bg-black/60" />
  <div className="relative z-10 max-w-3xl mx-auto px-6 text-center">
    <h2 className="text-4xl md:text-6xl font-display">Start Your Journey</h2>
    <p className="text-lg text-muted mt-4">Join thousands of creators.</p>
    <div className="flex justify-center gap-4 mt-8">
      <button className="bg-foreground text-background rounded-full px-8 py-4">Get Started</button>
      <button className="liquid-glass rounded-full px-8 py-4">Learn More</button>
    </div>
  </div>
</section>
```

## Simple Centered CTA

```tsx
<section className="bg-background py-20 px-6">
  <div className="max-w-2xl mx-auto text-center">
    <h2 className="text-4xl font-display">Ready to get started?</h2>
    <p className="text-muted mt-4">Join our newsletter.</p>
    <div className="mt-8 flex justify-center gap-4">
      <button className="bg-foreground text-background rounded-full px-8 py-3">Sign Up</button>
    </div>
  </div>
</section>
```

## Email Capture Form

```tsx
<form className="max-w-md mx-auto">
  <div className="liquid-glass rounded-full p-2 flex">
    <input
      type="email"
      placeholder="Enter your email"
      className="flex-1 bg-transparent px-4 outline-none"
    />
    <button className="bg-foreground text-background rounded-full px-6 py-2">
      Subscribe
    </button>
  </div>
</form>
```

## Split CTA (Left content, Right video)

```tsx
<section className="bg-background py-20 px-6">
  <div className="max-w-6xl mx-auto grid grid-cols-1 md:grid-cols-2 gap-12 items-center">
    <div>
      <h2 className="text-4xl font-display mb-4">Your next website starts here.</h2>
      <p className="text-muted mb-8">Book a free call.</p>
      <div className="flex gap-4">
        <button className="bg-foreground text-background rounded-full px-8 py-4">Book a Call</button>
      </div>
    </div>
    <div className="aspect-video rounded-3xl overflow-hidden">
      <video autoPlay loop muted playsInline className="w-full h-full object-cover">
        <source src={VIDEO_URL} type="video/mp4" />
      </video>
    </div>
  </div>
</section>
```

## Footer - Simple

```tsx
<footer className="bg-background py-12 px-6 border-t border-surface">
  <div className="max-w-6xl mx-auto flex flex-col md:flex-row justify-between items-center gap-6">
    <p className="text-sm text-muted">© 2026 Company. All rights reserved.</p>
    <div className="flex gap-6">
      <a href="#" className="text-sm text-muted hover:text-foreground">Privacy</a>
      <a href="#" className="text-sm text-muted hover:text-foreground">Terms</a>
      <a href="#" className="text-sm text-muted hover:text-foreground">Contact</a>
    </div>
  </div>
</footer>
```

## Footer with Social Links

```tsx
<footer className="bg-background pt-16 pb-8 px-6">
  <div className="max-w-6xl mx-auto">
    <div className="grid grid-cols-1 md:grid-cols-4 gap-12 mb-12">
      {/* Brand */}
      <div>
        <h3 className="font-display text-xl">Company</h3>
        <p className="text-sm text-muted mt-4">Description here.</p>
      </div>

      {/* Links */}
      <div>
        <h4 className="font-semibold mb-4">Product</h4>
        <ul className="space-y-2">
          <li><a href="#" className="text-sm text-muted">Link</a></li>
        </ul>
      </div>

      <div>
        <h4 className="font-semibold mb-4">Company</h4>
        <ul className="space-y-2">
          <li><a href="#" className="text-sm text-muted">Link</a></li>
        </ul>
      </div>

      {/* Social */}
      <div>
        <h4 className="font-semibold mb-4">Follow</h4>
        <div className="flex gap-4">
          <a href="#" className="liquid-glass rounded-full p-2"><Twitter className="w-5 h-5" /></a>
          <a href="#" className="liquid-glass rounded-full p-2"><Linkedin className="w-5 h-5" /></a>
          <a href="#" className="liquid-glass rounded-full p-2"><Github className="w-5 h-5" /></a>
        </div>
      </div>
    </div>

    <div className="border-t border-surface pt-8 flex flex-col md:flex-row justify-between">
      <p className="text-sm text-muted">© 2026 Company. All rights reserved.</p>
      <div className="flex gap-6 mt-4 md:mt-0">
        <a href="#" className="text-sm text-muted">Privacy</a>
        <a href="#" className="text-sm text-muted">Terms</a>
      </div>
    </div>
  </div>
</footer>
```

## Footer with Newsletter

```tsx
<footer className="bg-background pt-16 px-6">
  <div className="max-w-3xl mx-auto text-center pb-12">
    <h3 className="text-2xl font-display mb-4">Stay updated</h3>
    <p className="text-muted mb-6">Subscribe to our newsletter.</p>
    <form className="liquid-glass rounded-full p-2 flex max-w-md mx-auto">
      <input type="email" placeholder="Email" className="flex-1 bg-transparent px-4 outline-none" />
      <button className="bg-foreground text-background rounded-full px-6 py-2">Subscribe</button>
    </form>
  </div>
  <div className="border-t border-surface py-8 text-center text-sm text-muted">
    © 2026 Company
  </div>
</footer>
```

## Marquee CTA

```tsx
<div className="relative overflow-hidden py-12 bg-surface">
  <motion.div
    className="flex whitespace-nowrap"
    animate={{ x: ['0%', '-50%'] }}
    transition={{ repeat: Infinity, duration: 40, ease: 'linear' }}
  >
    {[...Array(10)].map((_, i) => (
      <span key={i} className="text-4xl font-display mx-8">
        BUILD THE FUTURE •
      </span>
    ))}
  </motion.div>
</div>
```

## Bottom Floating Nav

```tsx
<div className="fixed bottom-6 left-1/2 -translate-x-1/2 z-50">
  <div className="liquid-glass rounded-full px-8 py-3 flex items-center gap-4 shadow-lg">
    <span className="font-display text-xl">V</span>
    <button className="bg-foreground text-background rounded-full px-6 py-2">
      Start a chat
    </button>
  </div>
</div>
```

## GSAP Marquee Footer

```tsx
import { gsap } from 'gsap';

useEffect(() => {
  gsap.to(marqueeRef.current, {
    xPercent: -50,
    duration: 40,
    ease: 'none',
    repeat: -1,
  });
}, []);

<div ref={marqueeRef} className="py-12 overflow-hidden">
  <div className="flex">
    {words.map((word, i) => (
      <span key={i} className="text-6xl font-display mx-8">{word}</span>
    ))}
  </div>
</div>
```