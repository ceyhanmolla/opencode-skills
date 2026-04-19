# OpenCode Skills

Premium OpenCode skill'leri - direct copy-paste ready kod örnekleri ve referans rehberleri.

## Quick Start

```bash
# Skill'i yükle
skill({ name: "skill-name" })
```

## Mevcut Skilller

### hero-sections
Premium landing page bölümleri için kapsamlı referans. Video backgrounds, glassmorphism, typography, animations ve tüm sayfa bölümleri (Features, Testimonials, Stats, Pricing, CTA, Footer) dahil.

**Alt dosyalar:**
- `SKILL.md` - Ana referans + page structure
- `video-patterns.md` - Video entegrasyonları
- `liquid-glass.md` - Glassmorphism CSS
- `typography-patterns.md` - Font sistemleri
- `animation-patterns.md` - Animasyonlar
- `features-sections.md` - Features bölümleri
- `testimonials.md` - Testimonial bölümleri
- `stats-metrics.md` - İstatistik bölümleri
- `pricing.md` - Fiyatlandırma bölümleri
- `cta-footer.md` - CTA ve Footer

**Kullanım:**
```tsx
import { skill } from 'opencode';
skill({ name: "hero-sections" })
```

### design-taste-frontend
Senior UI/UX Engineering - Metrik bazlı tasarım kuralları, anti-slop kalıpları, Bento 2.0 spec. DESIGN_VARIANCE, MOTION_INTENSITY, VISUAL_DENSITY metrikleri ile premium frontend.

**Kullanım:**
```tsx
skill({ name: "design-taste-frontend" })
```

### web-page-design
Premium landing pages için video backgrounds, glassmorphic effects, cinematic animations rehberi. React + Vite + Tailwind + Framer Motion.

**Kullanım:**
```tsx
skill({ name: "web-page-design" })
```

## Teknolojiler

- React 18+ / Next.js
- Tailwind CSS v3/v4
- TypeScript
- Framer Motion
- GSAP (opsiyonel)
- hls.js (video streaming)

## Katkıda Bulunma

1. Fork repo
2. Yeni branch oluştur: `git checkout -b skill-name`
3. Değişiklikleri commit et: `git commit -m 'Add: new skill'`
4. Push et: `git push origin skill-name`
5. Pull request aç

## Lisans

MIT License