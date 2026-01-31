# 📽️ Spatial Memory Theater

An immersive, gesture-driven 3D experience for reliving your year's memories. Built with **Three.js** and **MediaPipe**, this application transforms your webcam into a spatial controller, allowing you to navigate a concave theater of your own photos.

![Interactive](https://img.shields.io/badge/Interactivity-Hand--Tracking-blueviolet)
![Tech](https://img.shields.io/badge/Tech-Three.js%20%7C%20MediaPipe-blue)
![Privacy](https://img.shields.io/badge/Privacy-Client--Side%20Only-green)

## 🌟 Features

- **Concave Theater Layout:** Memories are arranged in a curved, "IMAX-style" grid for maximum immersion.
- **Curved Image Geometry:** Each image is mathematically warped using CylinderGeometry to fit the curvature of the theater screen perfectly.
- **Raycast-Focusing:** Uses an invisible "laser" from the camera center to detect and focus on images instantly as you pan.
- **Hand-Gesture Navigation:** High-sensitivity tracking allows you to sweep through hundreds of photos with minimal hand movement.
- **Dynamic Spatial Zoom:** Stretching your hand (Pinching Out) expands the focused memory to cover **75% of your screen**.

---

## ✋ How to Control

| Action | Gesture | Result |
| :--- | :--- | :--- |
| **Navigate** | Move hand (natural pose) | Panning the theater wall left/right/up/down |
| **Focus** | Center an image | The bottom preview window updates automatically |
| **Zoom Out (Magnify)** | Spread Thumb & Index wide | Focused memory expands to 75% of screen |
| **Zoom In (Minimize)** | Bring fingers back together | Memory returns to the docked preview window |

---

## 🚀 Deployment Instructions (GitHub Pages)

1. **Upload** your `index.html` file to a new GitHub repository.
2. Go to **Settings > Pages**.
3. Under **Build and deployment**, set the branch to **main** and click **Save**.
4. After a minute, visit the URL provided (it must be `https://` for webcam access).
5. **Upload** your local photos and begin the experience.

---

## 🛠️ Tech Stack

- **[Three.js](https://threejs.org/):** Handles the 3D rendering, curved cylinder geometries, and raycasting.
- **[MediaPipe Hands](https://developers.google.com/mediapipe/solutions/vision/hand_landmarker):** Google's machine learning solution for real-time, low-latency hand tracking.
- **CSS3 Transforms:** Handles the smooth scaling of the focused UI container.

---

## 🔒 Privacy & Security

**Your privacy is the priority.** 
- All image processing is **client-side**. Your photos never leave your computer and are never uploaded to a server.
- The webcam stream is processed locally by the AI model to calculate coordinates; no video data is ever stored or transmitted.

---

## ⚙️ Customization

You can tweak the following constants in the `<script>` section of `index.html` to change the feel of the experience:

```javascript
const theaterRadius = 10;   // The depth of the theater curve
const cols = 6;              // Number of image blocks per row
const zoomThreshold = 0.22;  // Sensitivity for the zoom gesture
