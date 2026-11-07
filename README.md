<div align="center">

# 🪐 Losar 3D

### *An Immersive Audio-Reactive 3D Cosmic Odyssey*

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Flokeshnaivaidya-max%2FLosar)
[![React](https://img.shields.io/badge/React-17.0.1-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://reactjs.org/)
[![React Three Fiber](https://img.shields.io/badge/R3F-7.0.6-black?style=for-the-badge&logo=three.js&logoColor=white)](https://docs.pmnd.rs/react-three-fiber/)
[![Three.js](https://img.shields.io/badge/Three.js-0.131-049EF4?style=for-the-badge&logo=three.js&logoColor=white)](https://threejs.org/)
[![WebGL](https://img.shields.io/badge/WebGL-GLSL_Shaders-990000?style=for-the-badge&logo=webgl&logoColor=white)](https://www.khronos.org/webgl/)
[![Vercel Ready](https://img.shields.io/badge/Deployment-Vercel_Ready-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://vercel.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

<br />

<img width="100%" alt="Losar 3D Hero Banner" src="https://raw.githubusercontent.com/lokeshnaivaidya-max/Losar/main/losar-og.png" style="border-radius: 12px; box-shadow: 0 20px 40px rgba(0, 0, 0, 0.6);" />

<br />

<p align="center">
  <b>Explore celestial deformation, procedural space storms, and synchronized audio waves.</b>
  <br />
  A high-performance WebGL / Three.js experience reacting in real-time to frequency spectrums and musical beat drops.
</p>

[✨ Live Features](#-features) • [🚀 Quick Start](#-quick-start) • [⚡ Vercel Deployment](#-deployment-to-vercel) • [🛠️ Architecture](#%EF%B8%8F-architecture) • [📜 License](#-license)

</div>

---

## 🌟 Highlights

- **⚡ Modern Build Pipeline Fixed**: Ready for instant zero-config deployment on **Vercel**, **Netlify**, and modern Node (Node 18 / 20 / 22+).
- **🎶 Audio-Reactive Physics**: Real-time multi-track Web Audio API integration synchronizing planet deformations, wireframe bursts, and chromatic glitch effects.
- **🪐 Dynamic Celestial Shaders**: Custom GLSL vertex and fragment shaders creating silky, undulating textures across planetary surfaces.
- **🚀 Spline Flight Path**: Catmull-Rom curve navigation guiding a procedural spaceship through dense cosmic dust and asteroid fields.
- **✨ High-Performance Particle Engine**: Lorenz attractor sparks and instanced cosmic dust running at a silky-smooth 60 FPS.
- **🎨 Cinematic Post-Processing**: Full-screen post-processing pipeline featuring bloom, film grain, subtle glitch bursts, and soft-light color grading.

---

## 📸 Screenshots

| Deep Space Flight | Planetary Surface & Distortion |
| :---: | :---: |
| <img src="https://raw.githubusercontent.com/lokeshnaivaidya-max/Losar/main/screenshot-1.png" width="100%" /> | <img src="https://raw.githubusercontent.com/lokeshnaivaidya-max/Losar/main/screenshot-2.png" width="100%" /> |

---

## 🛠️ Tech Stack

- **Framework**: [React 17](https://reactjs.org/)
- **3D Graphics Engine**: [Three.js](https://threejs.org/)
- **React 3D Renderer**: [@react-three/fiber](https://github.com/pmndrs/react-three-fiber) & [@react-three/drei](https://github.com/pmndrs/drei)
- **State Management**: [Zustand](https://github.com/pmndrs/zustand)
- **Shaders & FX**: GLSL, `glslify`, `babel-plugin-glsl`, `glsl-film-grain`, `glsl-noise`, `glsl-blend-soft-light`
- **Audio API**: HTML5 Web Audio API & Audio Context Frequency Analyzer
- **Deployment Platform**: [Vercel](https://vercel.com/) / [Netlify](https://netlify.com/)

---

## 🚀 Quick Start

### Prerequisites

- **Node.js**: v16.x to v22.x (Recommended: Node 18 or 20 LTS)
- **Package Manager**: [Yarn](https://yarnpkg.com/) (recommended) or npm

### Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/lokeshnaivaidya-max/Losar.git
   cd Losar
   ```

2. **Install dependencies**:
   ```bash
   yarn install
   ```

3. **Start the development server**:
   ```bash
   yarn start
   ```
   Open [http://localhost:3000](http://localhost:3000) to view the application in your browser.

4. **Create a production build**:
   ```bash
   yarn build
   ```
   *Note: The build script automatically enables `--openssl-legacy-provider` to ensure seamless builds on modern Node.js runtimes.*

---

## ⚡ Deployment to Vercel

This repository is pre-configured with a root `vercel.json` and optimized npm scripts to deploy with zero manual configuration.

### One-Click Deploy

1. Push your repository to GitHub.
2. Go to [Vercel](https://vercel.com/new).
3. Import your `Losar` repository.
4. Leave all build settings as default:
   - **Framework Preset**: Create React App
   - **Build Command**: `NODE_OPTIONS=--openssl-legacy-provider react-scripts build` (auto-detected)
   - **Output Directory**: `build` (auto-detected)
5. Click **Deploy**!

> **💡 Note on OpenSSL Legacy Provider:**
> Node.js 17+ updated its default OpenSSL crypto providers. This repository pre-configures `NODE_OPTIONS=--openssl-legacy-provider` in `package.json` and `vercel.json`, completely resolving any `ERR_OSSL_EVP_UNSUPPORTED` errors during production builds.

---

## 🕹️ Controls & Interactions

- **🖱️ Mouse Movement**: Pans and rotates the cosmic viewing angle and camera perspective.
- **▶️ Play Button**: Unlocks the Web Audio Context and initiates musical playback with synchronized shaders.
- **📱 Responsive Zoom**: Automatically adjusts camera focal distance and field of view for mobile and desktop screens.

---

## 🏗️ Architecture

```
Losar/
├── public/                 # Static assets, 3D model (GLTF), audio tracks & manifest
│   ├── model.gltf          # Spaceship 3D model
│   ├── quitters-raga/      # Stems and audio files for Gold Panda - Quitters Raga
│   └── index.html          # HTML entry point with rich social meta tags
├── src/
│   ├── App.js              # Application root, canvas setup & audio state overlay
│   ├── Scene.js            # Main 3D scene holding planet, spaceship, dust & stars
│   ├── Planet.js           # Celestial mesh deformed by real-time audio frequencies
│   ├── SilkyMaterial.js    # Custom GLSL vertex and fragment shader material
│   ├── SpaceShip.js        # Spaceship model following Catmull-Rom spline curves
│   ├── SpaceDust.js        # Instanced particle nebula dust
│   ├── Sparks.js           # Lorenz attractor spark lines
│   ├── SparkStorm.js       # Dynamic storm particles reacting to bass spikes
│   ├── Music.js            # Web Audio API multi-track stem player and analyzer
│   ├── useMusicStore.js    # Zustand store controlling tracks, time, & audio peaks
│   ├── Effects.js          # Post-processing composer (bloom, grain, glitch)
│   └── styles.css          # Minimalist dark theme HUD styling
├── vercel.json             # Vercel deployment configuration
├── package.json            # Dependencies and OpenSSL-safe scripts
└── README.md               # Project documentation
```

---

## 👤 Author

**Lokesh Naivaidya**
- GitHub: [@lokeshnaivaidya-max](https://github.com/lokeshnaivaidya-max)
- Email: [lokesh.naivaidya@gmail.com](mailto:lokesh.naivaidya@gmail.com)

---

## 🎵 Music & Audio Credits

Featured musical track:
- **"Quitters Raga"** by [Gold Panda](https://www.youtube.com/watch?v=EeLlAg6GGLc)

---

## 📜 License

This project is open-source and available under the [MIT License](LICENSE).

<div align="center">
  <sub>Built with ❤️ by Lokesh Naivaidya</sub>
</div>
