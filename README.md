# Three.js Walking Animation (Offline Clone)

This project is a complete, offline-capable copy of the [Three.js Walking Animation](https://threejs.org/examples/#webgl_animation_walk) example. All libraries, 3D models, and textures have been downloaded and configured to run without an internet connection.

## Project Structure

```text
project-walk/
├── models/
│   └── gltf/
│       └── Soldier.glb           # 3D Animated Character
├── textures/
│   ├── equirectangular/
│   │   └── lobe.hdr              # Environment Lighting
│   └── floors/
│       ├── FloorsCheckerboard_S_Diffuse.jpg
│       ├── FloorsCheckerboard_S_Normal.jpg
├── jsm/                          # Three.js Modules
│   ├── controls/ OrbitControls.js
│   ├── libs/ lil-gui.module.min.js
│   ├── loaders/ GLTFLoader.js, HDRLoader.js
│   └── utils/ BufferGeometryUtils.js, SkeletonUtils.js
├── three.module.js               # Three.js Module Entry Point
├── three.core.js                 # Three.js Core Library
├── main.css                      # Styling
└── webgl_animation_walk.html     # Main Application File
```

## How to Run Offline

To bypass browser CORS restrictions for local files (especially 3D models and modules), you must run a local web server.

### Option 1: Using Python (Recommended)
If you have Python installed, run this command in the `project-walk` directory:
```bash
python -m http.server 8000
```
Then open: [http://localhost:8000/webgl_animation_walk.html](http://localhost:8000/webgl_animation_walk.html)

### Option 2: Using Node.js (http-server)
If you have Node.js installed:
```bash
npx http-server . -p 8000
```

## Controls

- **Movement**: Use `Arrow Keys` or `WASD`.
- **Run**: Hold `Shift` while moving.
- **Camera**: Left-click and drag to rotate, right-click and drag to pan, scroll to zoom.
- **Settings**: Use the GUI in the top-right corner to toggle the skeleton view or transition mode.

## Editing the Code

- Open `webgl_animation_walk.html` to modify the animation logic, lighting, or scene setup.
- To swap the model, replace `models/gltf/Soldier.glb` and update the loader path in the script (line 191).
- To change the floor, replace the textures in `textures/floors/`.

> [!TIP]
> All imports are handled via an `importmap` in the HTML file, making it easy to manage local dependencies without a build step.
