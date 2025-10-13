# 🎆 Fireworks WebGL Experience

A mesmerizing Three.js fireworks show that fills the browser with colorful particle bursts, smooth camera motion, and interactive controls. Whether you're looking for inspiration for your next creative coding project or a visual centerpiece for a celebration, this project turns your screen into a dynamic night sky.

## ✨ Highlights
- **Immersive particle effects** powered by custom GLSL vertex and fragment shaders.
- **Interactive camera controls** that respond to mouse movement and scroll wheel input.
- **Procedurally generated fireworks** for endless variety—no two shows are the same.
- **Touch and click support** so you can launch your own fireworks in real time.

## 🚀 Quick Start
This repository ships as a minimal Three.js experience that expects a modern bundler (e.g., [Vite](https://vitejs.dev/), [Parcel](https://parceljs.org/)) to resolve bare module imports. The steps below use Vite because it requires zero configuration for this setup.

```bash
# 1. Clone the repository
 git clone https://github.com/theaaravagarwal/fireworks.git
 cd fireworks

# 2. Initialize npm and add the required tooling
 npm init -y
 npm install three
 npm install --save-dev vite

# 3. Start the development server with Vite
 npx vite --open
```

> **Tip:** Prefer Parcel? Run `npm init -y`, install Parcel with `npm install parcel --save-dev`, and then launch with `npx parcel index.html`.

Once the dev server boots up, open the printed URL (usually http://localhost:5173) to watch the fireworks come alive.

## 🕹️ Controls
- **Move the mouse** to gently orbit the camera around the scene.
- **Scroll the mouse wheel** to zoom in and out.
- **Click or tap** anywhere on the canvas to instantly launch a new firework.

## 🛠️ Project Structure
```
├── index.html      # Minimal HTML shell that mounts the Three.js canvas
├── index.js        # Core Three.js logic, particle system, and animation loop
├── style.css       # Global styles (feel free to customize the ambiance)
└── README.md       # You're reading it!
```

## 🔍 How It Works
- Each firework launches as a single point that lerps toward a random destination.
- Upon reaching its peak, the firework spawns a burst of 80 particles with random offsets, all sharing a cohesive hue.
- Custom shader attributes animate point sizes, colors, and fade-out timing for a smooth, cinematic effect.
- A lightweight utility module keeps track of viewport size and mouse position so that camera motion feels responsive.

## 🎨 Make It Your Own
Looking to extend the experience? Try these ideas:
- **Color palettes:** Adjust the HSL values in `index.js` to create thematic shows (e.g., holiday colors, team colors).
- **Particle counts:** Increase the burst size or lifespan for dramatic finales.
- **Audio sync:** Trigger fireworks on beat detection from a music track using the Web Audio API.
- **UI overlay:** Add buttons to toggle auto-launch, change gravity, or reset the camera.

## 🤝 Contributing
Contributions are welcome! If you have ideas for new effects, performance improvements, or documentation updates:
1. Fork the repository and create a feature branch.
2. Commit your changes with descriptive messages.
3. Open a pull request describing your enhancements.

## 🧾 License
No license has been specified yet. If you plan to reuse or distribute this project, consider adding an open-source license (e.g., MIT, Apache 2.0) to clarify permissions.

## 🙌 Acknowledgements
- Built with [Three.js](https://threejs.org/)
- Inspired by the creative coding community and countless New Year celebrations.

Light up the night sky—share your screenshots, remixes, or live demos so others can experience your spin on the show! ✨
