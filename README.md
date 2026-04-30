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

### aura-asset-images

High-quality Unsplash-style görseller için Aura Asset Library entegrasyonu.

**Kullanım:**
```tsx
skill({ name: "aura-asset-images" })
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