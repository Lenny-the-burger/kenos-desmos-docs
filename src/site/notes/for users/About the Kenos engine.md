---
{"dg-publish":true,"permalink":"/for-users/about-the-kenos-engine/"}
---

# About the Kenos engine

The Kenos engine is a powerful ray-tracing engine that specializes in rendering static images. Currently, the engine only supports one method of global illumination, path tracing, but more options are planned in future updates.

Kenos is the spiritual successor to the 3-space raster engine, but does not share any code with its predecessor.

## Physically based rendering

Kenos follows the principles of physically based rendering, but in a limited capacity due to environment limitations. In the Desmos branch of Kenos, only three textures per material are used:

-   Albedo (colour)
-   Roughness
-   Normal

The engine supports textures up to 1000x1000 pixels in size. Additionally, it supports different types of lights, including point lights and area lights (though only square 2D planes are supported at the moment, they can be rotated, scaled, and positioned anywhere in the scene).

The light colour can not only be controlled by RGB values, but also by a kelvin value, as the engine has built-in support for blackbody simulation. This allows for more realistic lighting in the rendered scenes.