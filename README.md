# 🧩 3D Rubik's Cube Simulator

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Technology: Three.js](https://img.shields.io/badge/Technology-Three.js-blue.svg)](https://threejs.org/)

A fully interactive and responsive 3D Rubik's Cube simulator built using the powerful **Three.js** library for rendering and physics, and **Tailwind CSS** for a modern, sleek interface.



## ✨ Features

* **Interactive 3D Controls:** Use your mouse or touch to rotate the entire cube's view using Orbit Controls.
* **Layer Twisting:** Click and **drag/swipe** on any face to perform a 90-degree twist of that layer—mimicking a real-world Rubik's Cube.
* **Scramble Function:** Instantly randomize the cube with the **SCRAMBLE** button, executing a sequence of 25 random moves.
* **Responsive Design:** Optimized for both desktop and mobile devices.
* **Realistic Colors:** Uses standard Rubik's Cube color mapping (White, Yellow, Red, Orange, Blue, Green).

## 💻 Technologies Used

* **Three.js (r128):** Core library for creating and rendering the 3D cube.
* **OrbitControls.js:** Used for camera manipulation (rotating the view).
* **JavaScript (ES6):** Logic for interactions, rotations, and cube state management.
* **HTML5 / CSS3 (Tailwind CSS):** Markup and styling for the user interface.

## ⚙️ How It Works

The core of the simulator is built around Three.js objects and a custom rotation mechanism:

1. **Cubie Generation:** A 3x3x3 grid of `THREE.Mesh` objects (cubies) is created. Materials (colors) are assigned based on their initial position to form the classic solved state.
2. **Raycasting for Interaction:** A `THREE.Raycaster` is used to detect which face of which cubie the user has clicked/tapped on.
3. **Drag-to-Twist Logic:** Event handlers track the drag direction (horizontal/vertical swipe) and the clicked face's normal to mathematically determine the correct axis and direction for the 90-degree layer rotation.
4. **Pivot Rotation:** The 9 cubies in the target layer are temporarily attached to a single `THREE.Object3D` (a pivot). This pivot is animated to rotate $90^\circ$ around the correct axis.
5. **State Update:** After the animation, the cubies are detached from the pivot, and their final position and rotation are recalculated and snapped back onto the scene to maintain integrity for the next move.

## 🚀 Getting Started

### Prerequisites

You only need a modern web browser to run the simulator.

### Installation & Running Locally

1. **Clone the repository:**
    ```bash
    git clone https://github.com/TrushaSonawane/3D-Rubik-s-Cube-Simulator.git
    cd 3d-rubiks-cube-simulator
    ```
2. **Open the file:**
    Since the project uses external CDNs for Three.js and Tailwind CSS, you can simply open the `index.html` file directly in your web browser.

## 🤝 Contribution

Contributions are welcome! If you find a bug or have an idea for an improvement (e.g., move history, solving algorithm integration), feel free to open an issue or submit a pull request.

## 📜 License

This project is licensed under the MIT License.
