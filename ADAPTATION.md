# Scroll World → Magnific Adaptation

## 1. Reuse unchanged

- Keep the `ffmpeg` frame extraction and scrub-friendly H.264 encoding steps (`-g 8`, no audio, `faststart`, mobile encodes where needed).
- Copy `references/scrub-engine.js` unchanged; its blob loading, scroll scrubbing, crossfades, mobile handling, and reduced-motion fallback are provider-independent.
- Reuse `references/index-template.html`; only replace the theme colours, copy, and asset paths.

## 2. Rewrite for the Magnific MCP

- Replace Higgsfield/Monid CLI setup, authentication, model checks, job submission, polling, and downloads with Magnific MCP calls and creation identifiers.
- Use Magnific **Seedance 2.5** for the video chain. Verify its current settings and credit cost before rendering.
- Preserve the seam rule: extract the previous clip's actual last frame and the next clip's actual first frame with `ffmpeg`, upload them to Magnific, then pass them as the connector's **first-frame** and **last-frame** inputs.
- Use Magnific status/wait and result-download calls instead of parsing Higgsfield JSON files.

## 3. Rewrite the prompt style

- Replace the shared isometric clay-diorama preamble with a shared **dark cinematic BMW** preamble: photoreal automotive photography, matte black surfaces, near-black studio, red accent lighting, wet reflections, premium high contrast, shallow depth of field.
- Rewrite the scene-still template for full-bleed exterior, cockpit, detail, and driving scenes—not floating islands or miniature props.
- Rewrite leg/dive prompts as restrained cinematic camera moves around and through the car; remove isometric angles, opening roofs, toy-world language, and aerial diorama hops.
- Rewrite connector prompts to maintain the same black/red lighting, realistic scale, vehicle identity, and forward motion between the supplied first and last frames.
