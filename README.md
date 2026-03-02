# CSE 160 - Assignment 4 - Lighting
Name: Alexander Bateman  
Email: arbatema@ucsc.edu  

Live Demo: https://ycmsoft.github.io/Lighting/index.html

# Files:
- `index.html` - UI/canvas, lighting controls, loads all scripts.
- `src/World.js` - Main file: world rendering, game logic, input handling, textures, lighting setup.
- `src/Camera.js` - Camera class with movement, rotation, and mouse movement.
- `src/Cube.js` - Cube shape class with interleaved vertex/UV/normal buffer.
- `src/Sphere.js` - Sphere shape class with static vertex/normal buffer.
- `src/Model.js` - OBJ model loader adapted from lab.
- `src/Triangle.js` - Triangle drawing helpers.
- `src/Cylinder.js` - Cylinder shape class.
- `src/Circle.js` - Circle shape class.
- `lib/cuon-utils.js` - Shader utilities.
- `lib/cuon-matrix-cse160.js` - Matrix utilities.
- `lib/webgl-debug.js` - WebGL debugging utilities.
- `lib/webgl-utils.js` - WebGL utilities.
- `src/sky.jpg` - Sky texture (256x256).
- `src/brick.jpg` - Brick wall texture (256x256).
- `src/grass.jpg` - Grass ground texture (256x256).
- `src/teapot.obj` - Teapot OBJ model.
- `README.md` - This readme.

# Controls:
- Light ON/OFF - Toggle point light.
- Spotlight ON/OFF - Toggle spotlight.
- Normal ON/OFF - Toggle normal visualization.
- Animation ON/OFF - Toggle light orbit animation.
- Light X/Y/Z sliders - Move point light position (turn animation off first).
- Light R/G/B sliders - Change point light color.
- `W` - Move forward.
- `A` - Move left.
- `S` - Move backward.
- `D` - Move right.
- `Q` - Turn camera left.
- `E` - Turn camera right.
- Mouse - Rotate camera (click the canvas for pointer to lock).
- Left click - Place block.
- Right click - Remove block.
- Space - Jump.

# Notes to Grader:
- Turn animation off before using light position sliders (X and Z get overwritten by animation).


# Resources used:
Professor videos, links on the assignment page.

**World.js**: Consulted Claude for various debugging while building shaders, restructuring the fragment shader so point light and spotlight could be toggled independently, adding smoothstep for spotlight cutoff to remove hard edge line on sphere, and getting the spotlight to follow the orbiting light position in tick().

**Model.js**: Adapted most of it from the lab, but was getting errors with v/vt/vn stuff, asked Claude, it fixed it, (Lines 42-49) but it also added 
const line = lines[i].trim();
const tokens = line.split(/\s+/);