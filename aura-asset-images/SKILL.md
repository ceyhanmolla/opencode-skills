---
name: aura-asset-images
description: Use when searching for high-quality Unsplash-style images from Aura Asset Library
---

# Aura Asset Images

## Overview

Aura provides a searchable asset library at https://www.aura.build/assets with Unsplash-style images.

## How to Search

**Fast search using URL query:**
```
https://www.aura.build/assets?q=<tag>&order=popular
```

**Common tags:**
- `background`
- `abstract`
- `architecture`
- `portrait`
- `headshot`

**Workflow:**
1. Open https://www.aura.build/assets
2. Use search box or URL query with tag
3. Browse results, select 5 strong candidates
4. Return direct image URLs (format below)

## URL Formats

**Thumbnail format:**
```
https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/<UUID>_800w.jpg
```

**Higher resolution (recommended when available):**
```
https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/<UUID>_1600w.jpg
```

**If _1600w 404s:** Use _800w and instruct user to open asset page and download/export.

## Crop Ratios

| Use Case | Ratio | Description |
|---------|------|-------------|
| Avatars | 1:1 | Square |
| Headshots | 4:5 or 3:4 | Portrait |
| Website heroes | 16:9 | Large backgrounds |
| Mobile wallpapers | 9:16 | Stories |

**Cropping tips:**
- Faces: Keep eyes ~1/3 from top, avoid cutting chin/forehead
- Backgrounds: Preserve horizon lines, keep 30-50% negative space for text

## Curated Picks

### 1. Backgrounds (5)

- https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/fa51902b-c2a4-4c33-a96e-a8f1ef67edc6_3840w.jpg
- https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/d14dc069-558a-4c51-8aad-5cc237f9b61d_3840w.jpg
- https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/75134536-4198-40bf-9944-315511fe8c0b_3840w.jpg
- https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/c31dd008-598b-4fc9-b5c7-9c3e1d296d38_3840w.jpg
- https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/a4780cd9-2a3d-4bdc-9e5f-85a097b3a8bf_3840w.webp

**Suggested exports:**
- 16:9: 1920x1080, 2400x1350
- 9:16: 1080x1920

### 2. Abstract (5)

- https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/4734259a-bad7-422f-981e-ce01e79184f2_1600w.jpg
- https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/e534354d-c5f2-4399-a1d9-2f50338e8c47_1600w.jpg
- https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/d14dc069-558a-4c51-8aad-5cc237f9b61d_1600w.jpg
- https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/fa51902b-c2a4-4c33-a96e-a8f1ef67edc6_1600w.jpg
- https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/bfef5098-c30f-4cd9-b4ac-04b2673ab943_1600w.jpg

**Suggested exports:**
- Desktop wallpaper: 2560x1600 or 2880x1800
- Mobile wallpaper: 1080x1920

### 3. Architecture (5)

- https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/724142aa-44a6-48d3-9cf3-761e00d05b78_1600w.jpg
- https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/005600e5-f6ab-4e59-bc86-eaeb02797dfa_1600w.jpg
- https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/5ee0a38a-b5d3-4531-8793-98beed4af162_1600w.jpg
- https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/7f78131e-65e9-49b2-aa1f-ccc33e28df9f_1600w.webp
- https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/fb6415fd-bf4d-4ccf-8e9d-7ab445e99207_1600w.jpg

**Suggested exports:**
- Web hero: 2400x1350
- Feature section: 1600x900

### 4. Portraits (5)

- https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/0d868fef-f560-45ca-ab35-5dad4fc29059_3840w.webp
- https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/3186f9ea-5f5a-49f7-8fcf-568ad52f515e_3840w.webp
- https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/65695f80-23f9-46ee-8487-cbb6c93cc48b_3840w.webp
- https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/0d063fd9-f7c1-4536-ade0-9fd133f07279_3840w.webp
- https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/582afef4-b810-47b8-a047-8b3597c323e1_3840w.webp

**Suggested exports:**
- 3:4: 1500x2000
- 4:5: 1200x1500

### 5. Headshots (5)

- https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/2f563338-39fa-47ea-9761-658d4f3f84db_1600w.jpg
- https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/4f5668c5-fc4a-44e0-bc5e-a664189d3c31_1600w.jpg
- https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/eca707cc-a5b7-439a-b4fd-247f6106c2e1_1600w.jpg
- https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/77415a2e-dcbc-4748-a29d-fced4821881a_1600w.jpg
- https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/c92852bb-a510-405a-85ab-ffa0fde136a4_1600w.jpg

**Suggested exports:**
- 4:5: 800x1000, 1200x1500
- 1:1 variant: 512x512 (for avatar fallback)