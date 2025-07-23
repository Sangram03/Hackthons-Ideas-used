### 🌐 What is Three.js? – Full Detailed Guide

**Three.js** is a **JavaScript 3D library** that makes it **easier to create 3D graphics** in the browser using **WebGL**. With Three.js, you can build:

* 3D websites
* Interactive data visualizations
* VR/AR experiences
* Games
* 3D animations and simulations

---

## 🧠 Why Use Three.js?

Because **WebGL**, the browser’s 3D engine, is powerful but **low-level** and complex. Three.js simplifies WebGL by:

* Abstracting boilerplate setup code
* Providing intuitive classes for **camera**, **lights**, **meshes**, **geometry**, and **materials**
* Giving easy tools for **animation**, **controls**, and **loading 3D models**

---

## 🚀 Basic Concepts in Three.js

Let’s break down the key components of a basic Three.js scene.

### 1. ✅ Scene

The container that holds everything (camera, objects, lights, etc.)

```js
const scene = new THREE.Scene();
```

---

### 2. 🎥 Camera

The “eye” that views the scene.

```js
const camera = new THREE.PerspectiveCamera(
  75, // Field of view
  window.innerWidth / window.innerHeight, // Aspect ratio
  0.1, // Near plane
  1000 // Far plane
);
```

---

### 3. 🌍 Renderer

Renders the scene using WebGL.

```js
const renderer = new THREE.WebGLRenderer();
renderer.setSize(window.innerWidth, window.innerHeight);
document.body.appendChild(renderer.domElement);
```

---

### 4. 📦 Geometry + Material = Mesh (3D Object)

```js
const geometry = new THREE.BoxGeometry(1, 1, 1); // Cube
const material = new THREE.MeshBasicMaterial({ color: 0x00ff00 });
const cube = new THREE.Mesh(geometry, material);
scene.add(cube);
```

---

### 5. 💡 Lights

```js
const light = new THREE.PointLight(0xffffff, 1);
light.position.set(5, 5, 5);
scene.add(light);
```

---

### 6. 🌀 Animation Loop

```js
function animate() {
  requestAnimationFrame(animate);
  cube.rotation.x += 0.01;
  cube.rotation.y += 0.01;
  renderer.render(scene, camera);
}
animate();
```

---

## 🏁 Full Basic Example

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r148/three.min.js"></script>
<script>
  const scene = new THREE.Scene();
  const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
  const renderer = new THREE.WebGLRenderer();
  renderer.setSize(window.innerWidth, window.innerHeight);
  document.body.appendChild(renderer.domElement);

  const geometry = new THREE.BoxGeometry();
  const material = new THREE.MeshStandardMaterial({ color: 0x0077ff });
  const cube = new THREE.Mesh(geometry, material);
  scene.add(cube);

  const light = new THREE.PointLight(0xffffff, 1);
  light.position.set(10, 10, 10);
  scene.add(light);

  camera.position.z = 5;

  function animate() {
    requestAnimationFrame(animate);
    cube.rotation.x += 0.01;
    cube.rotation.y += 0.01;
    renderer.render(scene, camera);
  }

  animate();
</script>
```

---

## 🎯 Key Features

| Feature              | Description                                 |
| -------------------- | ------------------------------------------- |
| ✅ Scene Graph        | Easily structure and organize 3D elements   |
| 🖼️ Geometry Support | Built-in primitives like Cube, Sphere, etc. |
| ✨ Materials          | Basic, Lambert, Phong, Standard, etc.       |
| 💡 Lighting          | Ambient, Point, Directional, Spot, etc.     |
| 🔄 Animation         | Animate objects using rotation, time, etc.  |
| 🎮 Controls (Orbit)  | Zoom, pan, and rotate camera                |
| 🗂️ Model Loading    | Load GLTF, OBJ, FBX, STL, etc.              |
| 📦 Textures          | Add images or videos as material surfaces   |
| 🌈 Post Processing   | Effects like blur, bloom, etc.              |

---

## 🧩 Useful Add-ons

* **OrbitControls**: Rotate, zoom, and pan the camera interactively
* **GLTFLoader**: Load 3D models created in Blender or other 3D tools
* **Stats.js**: Performance monitor
* **dat.GUI**: UI sliders to tweak scene elements

---

## 🛠️ Real-World Use Cases

* **Portfolio websites** with 3D animation
* **Data visualization** in 3D
* **Online configurators** (e.g., car or product preview)
* **AR/VR experiences**
* **3D games** (with Three.js or integrating physics)

---

## 🧱 3D Model Support

Three.js supports importing many formats:

* `.glb` / `.gltf` (recommended, modern, lightweight)
* `.obj`
* `.fbx`
* `.stl`

Example:

```js
import { GLTFLoader } from 'three/examples/jsm/loaders/GLTFLoader.js';

const loader = new GLTFLoader();
loader.load('model.glb', (gltf) => {
  scene.add(gltf.scene);
});
```

---

## 📘 Resources to Learn

* 🔗 [Three.js Official Website](https://threejs.org/)
* 📚 [Three.js Docs](https://threejs.org/docs/)
* 🧪 [Three.js Examples Gallery](https://threejs.org/examples/)
* 🎮 [Three.js Journey Course](https://threejs-journey.com/) *(paid, excellent)*

---

