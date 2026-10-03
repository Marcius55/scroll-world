# M3 Noir Sequence

A scroll-controlled cinematic microsite built for the BMW M3 scroll-world assignment. The page turns seven generated video clips into one smooth journey: exterior studio, door opening, cabin entry, dashboard wake-up, cluster focus, console detail, and ambient interior lighting.

## Live website

Add the published URL here after deploying.

## GitHub repository

https://github.com/Marcius55/bmw-m3-scroll-world

## How it works

- `index.html` defines the identity, section copy, and clip order.
- `scrub-engine.js` maps scroll position to video time and preloads clips as blobs so scrubbing stays seekable.
- `assets/vid/*.mp4` contains the optimized scroll clips.
- `assets/poster/*.jpg` contains poster frames so the page never opens on blank video.

The clips are chained as a forward walkthrough. Each new generated clip was started from the previous clip's actual final frame, then the page uses a short crossfade to hide small model re-render shifts.

The current generated video masters are 480p previews, so they are intentionally lightweight but will look softer when stretched full-screen. A sharper final version would require regenerating or finalizing the video chain at a higher resolution.

## Run locally

Use any static server from the project folder:

```bash
python -m http.server 8080
```

Then open `http://localhost:8080`.

## Credits / production notes

Images were generated with GPT 2.5 and video clips with Seedance 2.5 through Magnific. The final page does not generate anything at runtime; it only plays local static media files.
