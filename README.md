# 🌍 Hand-Controlled Globe

An interactive **3D Earth** that responds to **real-time hand gestures** using a webcam.
Rotate, zoom, and flick the globe naturally — no mouse, no controller, just your hands.

Built using **Three.js**, **MediaPipe Hands**, and **WebGL**, this project explores intuitive, embodied interaction with digital objects.

---

## ✨ Features

* **Real-time hand tracking** using MediaPipe
* **Natural rotation control** via finger direction & palm angle
* **Gesture-based zoom** using hand openness
* **Pause & resume zoom** with seamless recalibration
* **Two-finger flick inertia** for kinetic globe movement
* **Smooth motion filtering** to reduce jitter
* **Optional hand skeleton overlay**
* **Optional live video feed**
* Fully **web-based** — runs in the browser

---

## 🖐️ Gesture Controls

| Gesture                           | Action                    |
| --------------------------------- | ------------------------- |
| Rotate index finger around palm   | Rotate the globe          |
| Open hand                         | Zoom out                  |
| Closed hand                       | Zoom in                   |
| Space bar / Pause button          | Pause or resume zoom      |
| Two fingers up + horizontal flick | Add rotational inertia    |
| Calibration buttons               | Set min/max hand openness |

---

## 🧠 How It Works

### 1. Hand Tracking

* Uses **MediaPipe Hands** to detect 21 hand landmarks.
* Calculates **average distance between palm & fingertips** to determine hand openness.

### 2. Zoom Logic

* Hand openness is normalized between **calibrated closed & open states**.
* Zoom is applied by scaling the globe smoothly.
* When paused, the system **locks scale** and intelligently waits for meaningful hand movement before resuming (prevents jumps).

### 3. Rotation System

* Globe rotation is driven by the **angular change** between palm and index finger.
* Supports **velocity-based inertia** with natural decay.

### 4. Rendering

* Globe is loaded via **GLTFLoader** (`Earth.glb`)
* Scene is normalized automatically for consistent scale across models.
* Lighting uses ambient + directional light for depth.

---

## 🛠️ Tech Stack

* **Three.js** – 3D rendering
* **MediaPipe Hands** – Real-time hand tracking
* **WebGL** – GPU-accelerated graphics
* **JavaScript (ES Modules)**
* **HTML5 Canvas**

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/hand-controlled-globe.git
cd hand-controlled-globe
```

### 2. Add the Globe Model

Place `Earth.glb` in the root folder:

```
/hand-controlled-globe
 ├─ index.html
 ├─ Earth.glb
```

### 3. Run a Local Server

> MediaPipe requires HTTPS or localhost.

```bash
# Python
python -m http.server

# OR Node
npx serve
```

Open:

```
http://localhost:8000
```

---

## ⚠️ Requirements

* Webcam access
* Modern browser (Chrome / Edge recommended)
* HTTPS or localhost environment

---

## 🧪 Known Limitations

* Designed for **single-hand interaction**
* Performance depends on webcam quality & lighting
* Requires calibration per user for best accuracy

---

## 🌱 Future Improvements

* Two-hand interaction (pan + scale)
* Touch & mouse fallback controls
* Gesture presets / sensitivity profiles
* Dynamic globe textures (day/night, clouds)
* VR / AR extension

---

## 📸 Demo

> Add a GIF or screen recording here for maximum impact.

---

## 📄 License

MIT License — free to use, modify, and build upon.

---

## 🙌 Credits

* **MediaPipe Hands** – Google
* **Three.js** – Three.js contributors

---

Just tell me what you want next 👌
