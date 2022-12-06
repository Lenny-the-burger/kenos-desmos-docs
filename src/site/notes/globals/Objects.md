---
{"dg-publish":true,"permalink":"/globals/objects/"}
---

# Objects

## TotalObj 
The total number of objects in the scene.

## CameraRot 
The rotation of the camera in the scene, specified as 3D coordinates (x, y, z).

## Scene Position Array (`scenePosArr`)

The `scenePosArr` is an array that contains the position coordinates (x, y, z) for each object in the 3D scene. These coordinates determine where the object is located in the 3D space. The values are stored one after another in the array, with each set of x, y, z coordinates representing a single object.

For example, if the `scenePosArr` contains the following values: `[1, 2, 3, 4, 5, 6]`, this means that there are two objects in the scene with the following position coordinates:

-   Object 1: x = 1, y = 2, z = 3
-   Object 2: x = 4, y = 5, z = 6

## Scene Rotation Array (`sceneRotArr`)

The `sceneRotArr` is an array that contains the rotation coordinates (x, y, z) for each object in the 3D scene. These coordinates determine the orientation of the object in the 3D space. The values are stored one after another in the array, with each set of x, y, z coordinates representing a single object.

For example, if the `sceneRotArr` contains the following values: `[45, 60, 90, 0, 0, 0]`, this means that there are two objects in the scene with the following rotation coordinates:

-   Object 1: x = 45, y = 60, z = 90
-   Object 2: x = 0, y = 0, z = 0

## Scene Scale Array (`sceneScaleArr`)

The `sceneScaleArr` is an array that contains the scaling coordinates (x, y, z) for each object in the 3D scene. These coordinates determine the size of the object in the 3D space. The values are stored one after another in the array, with each set of x, y, z coordinates representing a single object.

For example, if the `sceneScaleArr` contains the following values: `[1, 2, 3, 0.5, 0.5, 0.5]`, this means that there are two objects in the scene with the following scaling coordinates:

-   Object 1: x = 1, y = 2, z = 3
-   Object 2: x = 0.5, y = 0.5, z = 0.5

