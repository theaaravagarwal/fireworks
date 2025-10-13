# Fireworks WebGL Showcase

Fireworks WebGL Showcase is an interactive Three.js experiment that fills the browser with a steady stream of colorful fireworks. Particle systems, custom GLSL shaders, and smooth camera easing create an atmospheric display that responds to pointer movement and clicks/taps.

https://github.com/<your-username>/fireworks/assets/cover-image.png

## ✨ Features

- **Immersive particle fireworks** powered by Three.js points and shader materials.
- **Custom GLSL shaders** for per-particle color/alpha blending and depth-aware sizing.
- **Interactive camera controls** that react to mouse/touch movement and scroll-wheel zoom.
- **Autonomous firework launcher** that keeps the sky alive while supporting manual bursts on click/tap.
- **Responsive full-screen canvas** that adapts to any viewport size.

## 🚀 Quick start

The project is a small, framework-free setup that expects modern browsers with ES modules. The recommended way to develop locally is with [Vite](https://vitejs.dev/) because it resolves bare module imports like `three` out of the box.

```bash
# Clone and move into the project
git clone https://github.com/<your-username>/fireworks.git
cd fireworks

# Initialize a package manifest (if you don't already have one)
npm init -y

# Install runtime and dev dependencies
npm install three
npm install --save-dev vite

# Launch a hot-reload dev server
npx vite --host --open
```

Vite will serve `index.html` as the app entry point and automatically resolve the module imports defined in `index.js`.

> **Alternative:** If you prefer another bundler such as Parcel, webpack, or Snowpack, simply ensure the `three` dependency is installed and point the bundler at `index.html`.

## 🧠 Project structure

```text
fireworks/
├── index.html    # Minimal HTML shell that mounts the WebGL canvas
├── index.js      # Three.js scene setup, particle system, shaders, and interaction logic
├── style.css     # Full-screen canvas styling
└── README.md     # Documentation (you are here!)
```

### Key implementation details

- **`Firework` class** (in `index.js`) spawns a launch particle, waits briefly, then explodes into 80 shader-driven particles that fade over time.
- **Custom shader uniforms** control particle size and per-vertex color. Alpha values decay to create a natural dissipating effect.
- **`Utils` helper** captures viewport size and pointer position to keep the simulation responsive.
- **Camera easing** lerps toward the pointer position (`to.px`, `to.py`, `to.pz`) for a cinematic parallax effect.

## 🎮 Interaction guide

- Move the mouse (or drag on touch devices) to pan the camera across the fireworks.
- Scroll to zoom the camera in/out and change the perspective depth.
- Click or tap anywhere on the canvas to trigger an immediate firework burst.
- Enjoy the autonomous launcher that continues to introduce random fireworks in the background.

## 🎨 Customization ideas

| Area | How to customize |
| --- | --- |
| Particle count | Adjust the `80` constant inside `Firework.prototype.explode` to spawn more or fewer fragments. |
| Color palette | Modify the `color.setHSL` calls in `launch` and `explode` to experiment with different hues/saturation. |
| Lifespan & fade | Change `lifespan` and the interpolation factor in `update` to control how long trails stay visible. |
| Camera behavior | Tweak the lerp divisors in the animation loop or clamp `to.pz` to limit zoom range. |
| Spawn rate | Edit the random check in the `draw` loop to increase/decrease auto-generated fireworks. |

## 🧪 Development tips

- Keep an eye on browser dev tools to monitor the frame rate—particle-heavy scenes may require tuning on lower-powered devices.
- When deploying, consider minifying or bundling assets and hosting them via a static site service (GitHub Pages, Netlify, Vercel, etc.).
- If you extend the project, TypeScript support works well with Three.js; add `tsconfig.json` and rely on `three`'s TypeScript declarations.

## 🤝 Contributing

Issues and pull requests are welcome! Ideas for contributions include:

- Performance optimizations (e.g., instanced rendering, GPU-based particle updates)
- Accessibility enhancements (UI controls, keyboard shortcuts)
- New visual effects (trails, sound, different particle geometries)

Please open an issue to discuss significant changes before submitting a PR.

## 📄 License

This repository does not yet include a license file. If you plan to reuse or distribute the project, please add an appropriate license (for example, MIT) to clarify usage terms.

## 🙌 Acknowledgements

- [Three.js](https://threejs.org/) for the core rendering engine.
- The WebGL community for continual inspiration on creative coding projects.

Enjoy painting the sky with code! ✨
