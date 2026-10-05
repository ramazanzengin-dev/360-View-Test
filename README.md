# 360-View-Test (zp360.js) 🚀

Developed by **Ramazan Zengin** (Software Developer at **Zümrüt Plastik**)

An ultra-lightweight, high-performance, and memory-optimized **360-degree interactive product viewer** built from scratch using pure JavaScript. This engine is designed to showcase industrial products (such as store fixtures, baskets, and display stands) seamlessly on e-commerce and retail websites.

---

## 💡 Key Features & Architecture

- **Zero Dependencies (Vanilla JS):** Built with 100% pure JavaScript (`zp360.js`). It does not rely on heavy frameworks or external libraries like React, Next.js, jQuery, or Three.js. This ensures maximum page loading speed (improving LCP and Core Web Vitals).
- **Circular Array Rotation Algorithm:** Utilizing mathematical logic and modular arithmetic, the engine tracks user drag interactions (mouse/touch pixels) and maps them smoothly across 36 sequenced product frames (shot at 10-degree increments) for an infinite, continuous 360° rotation loop.
- **Low-Level Memory Management Culture:** Heavily inspired by memory optimization techniques found in **C++ and Assembly**. 
  - **Asynchronous Image Preloading:** All sequenced WebP images are loaded asynchronously into browser RAM upon initialization, avoiding network lags, flickering, or white screens during user interaction.
  - **Garbage Collection Optimization:** Instead of creating and destroying multiple DOM Image objects dynamically, the engine keeps a static array cache and strictly mutates a single `<img>` source reference, keeping CPU and RAM utilization at an absolute minimum.
- **Responsive & Mobile-First Touch Interactions:** Fully integrated touch event listeners (`touchstart`, `touchmove`) with scaled drag-to-rotation ratios tailored for mobile and tablet devices.

---

## 🛠️ Tech Stack & Languages

- **Primary Language:** JavaScript (ES6+ Vanilla JS)
- **Low-Level Logic Foundation:** C, C++, Assembly (Principles applied to core algorithmic efficiency and data-structure caching)
- **Asset Format:** WebP (Optimized for hardware-accelerated GPU rendering)

---

## 🚀 Quick Setup & Usage

To integrate `zp360.js` into your product view container, simply include the script and initialize it with your sequenced asset array:

```javascript
// Example initialization
const viewer = new ZP360Viewer({
  containerId: 'product-360-container',
  imagePath: './sepet-360/',
  totalFrames: 36,
  autoRotate: true,
  dampingFactor: 0.95
});
```

---
*Developed for digital transformation and 3D product simulation solutions at Zümrüt Plastik.*
