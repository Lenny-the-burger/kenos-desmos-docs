---
{"dg-publish":true,"permalink":"/for-users/about-the-kenos-engine/"}
---

# About the Kenos engine
The Kenos engine is a powerful ray-tracing engine focused on rendering static images. Currently the engine only supports one methods of global illumination, path tracing, but more are planned.

Kenos is the spiritual succesor to the 3-space raster engine, but doe snot share any code. 

## Physically based rendering
Kenos follows the principles of physically based rendering, but in a limited way. This is partly due to environment limitations. The Desmos branch of Kenos only uses three textures per material:
- Albedo (colour)
- Roughness
- Normal