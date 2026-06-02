# axe-historique

An experiment with the [HTML-in-Canvas API](https://developer.chrome.com/blog/html-in-canvas-origin-trial), a new web platform feature that lets you render live, interactive HTML elements directly into `<canvas>`, WebGL, and WebGPU contexts while preserving accessibility and interactivity. The API entered origin trial at Google I/O 2026 and is available in Chromium-based browsers (146+) behind the `chrome://flags/#canvas-draw-element` flag.

## Sources

This project is based on the following videos:

- [Build next-generation UIs with the HTML-in-Canvas API](https://www.youtube.com/watch?v=TUtKGTeFWjQ) — Chrome for Developers overview of the API, covering how HTML elements can be drawn into canvas while keeping semantics, accessibility, and interactivity.
- [HTML in Canvas is Futuristic AF - Tutorial](https://www.youtube.com/watch?v=Z1VBHgTLQVc) — Hands-on tutorial showing what you can build with the API, including per-pixel distortion, scanline transitions, and shader-based effects on live DOM.

## Background

The HTML-in-Canvas API exposes three primitives:

- A `layoutsubtree` attribute that opts canvas children into layout.
- A `drawElement` / `texElementImage2D()` method for drawing an element into a 2D context or uploading it as a WebGL/WebGPU texture.
- A `paint` event that fires when children change.

This unlocks effects that pure CSS transforms can't do — barrel-distorting rendered text, warping half of an input, blending light and dark themes as textures, and other shader-driven manipulations of real DOM.
