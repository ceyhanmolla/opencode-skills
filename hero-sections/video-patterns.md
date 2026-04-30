# Video Patterns

## Basic Video Background

```tsx
<video
  autoPlay
  loop
  muted
  playsInline
  className="absolute inset-0 w-full h-full object-cover"
>
  <source src="URL" type="video/mp4" />
</video>
```

## Fade-In/Out Loop

```tsx
const VideoWithFade = ({ src }: { src: string }) => {
  const videoRef = useRef<HTMLVideoElement>(null);
  const [opacity, setOpacity] = useState(0);
  const fadingOutRef = useRef(false);

  useEffect(() => {
    const video = videoRef.current;
    if (!video) return;

    const fadeIn = () => {
      let currentOpacity = 0;
      const animate = () => {
        currentOpacity += 0.02;
        if (currentOpacity >= 1) {
          setOpacity(1);
          return;
        }
        setOpacity(currentOpacity);
        requestAnimationFrame(animate);
      };
      animate();
    };

    const fadeOut = () => {
      if (fadingOutRef.current) return;
      fadingOutRef.current = true;

      let currentOpacity = opacity;
      const animate = () => {
        currentOpacity -= 0.02;
        if (currentOpacity <= 0) {
          setOpacity(0);
          return;
        }
        setOpacity(currentOpacity);
        requestAnimationFrame(animate);
      };
      animate();
    };

    const handleTimeUpdate = () => {
      const remaining = video.duration - video.currentTime;
      if (remaining <= 0.55 && !fadingOutRef.current) {
        fadeOut();
      }
    };

    const handleEnded = () => {
      setOpacity(0);
      fadingOutRef.current = false;
      setTimeout(() => {
        video.currentTime = 0;
        video.play();
        fadeIn();
      }, 100);
    };

    video.addEventListener('canplay', () => { video.play(); fadeIn(); });
    video.addEventListener('timeupdate', handleTimeUpdate);
    video.addEventListener('ended', handleEnded);

    return () => {
      video.removeEventListener('canplay', () => video.play());
      video.removeEventListener('timeupdate', handleTimeUpdate);
      video.removeEventListener('ended', handleEnded);
    };
  }, [opacity]);

  return (
    <video
      ref={videoRef}
      autoPlay
      muted
      playsInline
      style={{ opacity }}
      className="absolute inset-0 w-full h-full object-cover"
    >
      <source src={src} type="video/mp4" />
    </video>
  );
};
```

## HLS Stream

```tsx
import Hls from 'hls.js';

const HlsVideo = ({ src }: { src: string }) => {
  const videoRef = useRef<HTMLVideoElement>(null);

  useEffect(() => {
    const video = videoRef.current;
    if (!video) return;

    if (Hls.isSupported()) {
      const hls = new Hls({ enableWorker: false });
      hls.loadSource(src);
      hls.attachMedia(video);
      return () => hls.destroy();
    } else if (video.canPlayType('application/vnd.apple.mpegurl')) {
      video.src = src;
    }
  }, [src]);

  return (
    <video ref={videoRef} autoPlay loop muted playsInline className="absolute inset-0 object-cover" />
  );
};
```

## Common Video URLs

| Service | URL Pattern |
|---------|------------|
| CloudFront | https://d8j0ntlcm91z4.cloudfront.net/... |
| Mux | https://stream.mux.com/...m3u8 |
| Generic MP4 | .mp4 with autoPlay loop muted playsInline |

## Overlays

### Gradient Overlay
```tsx
<div className="absolute inset-0 bg-gradient-to-b from-black/60 via-transparent to-black/60" />
```

### Simple Dark Overlay
```tsx
<div className="absolute inset-0 bg-black/50" />
```

## Z-Index Layering

```tsx
<section className="relative h-screen overflow-hidden">
  <video className="absolute inset-0 z-0" />     {/* Background */}
  <div className="absolute inset-0 z-10" />    {/* Gradient */}
  <div className="relative z-20" />          {/* Content */}
</section>
```

## Mobile Considerations

- Always use `playsInline` for iOS compatibility
- Consider `preload="auto"` for above-the-fold videos
- Add poster image fallback

```tsx
<video poster="/images/hero-poster.jpg" ... />
```