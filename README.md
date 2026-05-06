# custom-landings

This repository is a small collection of standalone projects with **3 modern landing pages**:

- `camera-landing`
- `iphone-landing`
- `keyforge-landing`

Each project is its own Astro landing page with its own files, assets, and setup.

## What these landing pages do

All three demos use **AI-generated hero videos** that are revealed through scroll. The visual idea is that the product starts as separated or fragmented pieces and then feels like it recomposes as you keep scrolling.

That fragmented look comes from the video content itself. The JavaScript does not split the video in the browser. Instead, it connects page scroll to the video's playback position so the animation moves forward or backward with your scroll.

## How the scroll script works

In simple terms, the script:

1. Measures how far you have scrolled through the hero section.
2. Converts that progress into a target time inside the video.
3. Smoothly moves the current video time toward that target with `requestAnimationFrame`.
4. Waits for each seek to finish before sending the next one, which keeps the motion stable.
5. Shows or hides text slides at specific scroll ranges in the landings that use them.

There is also a reduced-motion fallback: if the user prefers reduced motion, the video plays normally in a loop instead of being scrubbed by scroll.
