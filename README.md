<p align="center">
<img width="600" height="300" alt="resopulse-logo-github" src="https://github.com/user-attachments/assets/60cb9d65-a17b-4c91-918c-0833ba8a3a4d" />
</p>

<div align="center">

[![Three.js](https://img.shields.io/badge/Three.js-r128+-black?style=for-the-badge&logo=three.js&logoColor=white)](https://threejs.org/)
[![WebGL](https://img.shields.io/badge/WebGL-GLSL-red?style=for-the-badge)](https://get.webgl.org/)
[![Vite](https://img.shields.io/badge/Vite-Bundler-646CFF?style=for-the-badge&logo=vite&logoColor=white)](https://vitejs.dev/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

</div>

## Overview
ResoPulse is an reactive-motion music visualizer that includes a movable icosahedron which pulses out particles for each audio peak detected from an user-input audio file. The music visualizer is developed as a team class project for our graduate Computer Animation class, and it is made using JavaScript, specifically the THREE.js library, Vite, and WebGL.

## Display
<img width="1918" height="957" alt="Screenshot 2025-12-11 112515" src="https://github.com/user-attachments/assets/910ee4d0-b66c-4c4e-ad73-9d27f5185856" />

## Key Features
### Adaptive Audio Intelligence
ResoPulse utilizes the THREE.js library to compile standard frequency bands into rhythm data in three ways.
* **Multi-Band Averaging** - The icosahedron aggregates data from several close frequency bands to identify distinct instrumental triggers.
* **Kick & Bass Detection** - Specialized detection for "kick" (8–18 Hz) and "bass" (18–40 Hz) bands drives specific visual activations like object spins and particle bursts.
* **Intensity-Based Activation** - Visual effects are triggered not just by volume, but by the "intensity" of a peak—the delta between current volume and previous averages.

### Procedural and Interactive Visuals
ResoPulse is designed with immersive visuals with many comto enhance the music visualizer.
* **Dynamic Spline Navigation** - A looping Catmull-Rom curve is used to couple object’s velocity to the overall audio volume.
* **Newtonian Particle Engine** - A particle system is implemented to control burst particles, where particle count and burst speed are determined by the "intensity" of the detected peak.
* **Interactive UI** - A heuristic control panel is built, allowing users to manually tune frequency ranges, volume thresholds, and boost amounts to suit different genres like EDM or Hardcore Techno.

## Technical Features
### The Peak Detection Algorithm
To achieve a "rhythmic" feel, the engine monitors the audio spectrum for instantaneous spikes:
* **Logarithmic Scaling** - ResoPulse simulates a logarithmic feel to better capture human auditory perception as compared to standard FFT analysis, which provides linear scaling.
* **Activation States** - When a frequency average exceeds the previous average by a specific margin, an "activation state" is toggled.
* **Cooldown Logic** - Prevents visual clutter by implementing a "boost cooldown" (default 0.1s) after an audio peak is detected.

## Installation
First, clone this repository using this command:
```
git clone https://github.com/AparCode/resopulse.git
```

Then, run the npm install command. This installs all of the JavaScript dependencies for this project:
```
npm install
```

Finally, run the program using the npm run command:
```
npm run dev
```
## How to Use
1. Use the "Choose File" button to upload any local .mp3 or .wav file.
2. Adjust the "Min Volume Differ" and "Boost Amount" sliders to calibrate the visualizer to your specific track.
3. Move the camera freely using the mouse via the built-in Orbit Controller.

## Future Work
In the future, we plan to update and enhance ResoPulse through
* **Optimization** - Reduce the dependency of audio analysis on the renderer's framerate to ensure consistent detection on lower-end devices.
* **Customization** - Add user controls for particle color, shape, and effect type.
* **Audio Features** -Implement surround sound functionality and automatic parameter tuning based on source audio properties.


