---
{"dg-publish":true,"permalink":"/structs/mesh/"}
---

# Mesh 🔳
Individual models imported into the engine. Multiple scene objects can use the same mesh with independent world space position, scaling, and rotation.


## Constructor
A mesh consists of six arrays:

| Name | Description | 
| --- | --- | 
| Vertices X array (Vx) | Contains x component of each mesh vertex |
| Vertices Y array (Vy) | Contains y component of each mesh vertex |
| Vertices Z array (Vz) | Contains z component of each mesh vertex |
| Face vertex 1 array (F1) | Contains the index of the first vertex in each face |
| Face vertex 2 array (F2) | Contains the index of the second vertex in each face |
| Face vertex 3 array (F3) | Contains the index of the third vertex in each face |

Each component of vertex vectors are stored seperatly, where each one vertex can be obtained by `[Vx[n], Vy[n], Vz[n]]`.

Each mesh face is a triangle so consists of three vertices, these can be obtained using the face vertex arrays: `[V[F1[n], V[F2[n], V[F3[n]]`.

 ## Methods
List of methods associated with the mesh object.
- <font face="consolas"> <font color="green">num[]</font> getMeshVrtxArr( <font color="green">num</font> msh, <font color="purple">enum</font> axis )</font> 
	>Get mesh vertex array for `axis` axis, where `axis` is a mesh axis enum and `msh` is global mesh id. Returns basically x_m from 3-space etc.
- <font face="consolas"> <font color="blue">vec3</font> getObjProp( <font color="orange">scene_obj</font> obj, <font color="purple">enum</font> prop )</font>
	>Returns the requested property `prop` of scene object `obj`. `prop` must be an object property enum.
	>All values are returned as a vec3, values that are not vectors are still returned as vec3 but can be used in indexing.
- <font face="consolas"> <font color="blue">vec3</font> getMeshVrtx( <font color="green">num</font> msh, <font color="green">num</font> idx )</font>
	>Returns the vertex at index `idx` of mesh `msh`, where `msh` is global mesh id.
- <font face="consolas"> <font color="green">num</font> getMeshSize( <font color="green">num</font> msh)</font>
	>Returns the size of the mesh (how many vertices), where `msh` is global mesh id.

#### Internal methods
- <font face="consolas"> <font color="red">INTERNAL</font> <font color="green">num[]</font> get{object}VrtxArr( <font color="purple">enum</font> axis )</font>
	>Does the same thing as getMeshVrtxArr but one of these is created for every mesh, and is mesh specific. Will probably change how this works but this is fine for now, we will only have like 3 meshes max.

## Enums
#### Mesh axis enums:
- MshX
- MshY
- MshZ