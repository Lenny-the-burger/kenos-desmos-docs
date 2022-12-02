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

Each component of vertex vectors are stored seperatly, where each one vertex can be obtained by  ![mesh1](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAD0AAABACAQAAAAD17d9AAAABGdBTUEAALGPC/xhBQAAACBjSFJNAAB6JgAAgIQAAPoAAACA6AAAdTAAAOpgAAA6mAAAF3CculE8AAAAAmJLR0QA/4ePzL8AAAAJcEhZcwAADsQAAA7EAZUrDhsAAAAHdElNRQfmDAIRFyapWr+ZAAADCUlEQVRYw+2Z/XGqQBTFf/eNBTApYe0A8yp4pAOMHawdkEkFGdOBSQWJdgAdJNqBlqB0cN8foOFjMRLlzbwZDjMKu6xn74d3Dyz46PFYKN0e7L8uBgCMyJDSNf7k37fMwUevYs+GmLChLyJmVWrx84/KbRu0+DPEKDHBN9Rxm34ntUKE4pVui86wujX1L0c8toApXE/0uYuwf0stEfNuMm5wmloMqW6/uiTkhhEzDIaRTuuDxeKR8o4lZcyDrpvJHRnOnnl+Niu1BwQKASsCDHv8aiwxhBj2WEXBfkX4vFjDltvcgrKz7zTJpqsJO54cFvm6JGCnLwB4pypFE7UBMVB0NuhDNgGWoKkr+XR56M/v/GhP7QHTfO5VhLxxCgExgHgEx0mcTb0BmVUzWzyJQHwMCYBErqFi8PgE4J61biVsazVVZwP3TIEg6xXbYFHAVlMARiSUK0QJA2frJ+s8rkUkjMSSkPAoGz5rU8swPHprzkTsqXJ0reXjKoX0H6GnvgypxE1/JIkkxpGUV0qzlknZp9l/TC2b02kmq3p7r0gz9Iq0qkgDPCY6zs/9uj/OV6QOak0lZZhfTIvrtngYfZFX8XUNPGRCqERs2JGwAn0GgRl3bRzerEgD3sXHyy0JMqFUQmeKdKkpk0wYiQ91Z3arSA961GXzwTfXVqQ5DOvcotjV3Y0iPWAHYhqt7kSRZpjyKjEjV6SB7hUps+orn84Vqazy2Fme2o2so+2iuSMBmTufMlti0PL+BfcyJNZly3GXUzc8ewKkEjN3T0ki7npFmqGnvgi9Iu0V6Y+pq4oUQBaylxAkFK8+WKxEYsWTSKzE4jdTt1KkuRdi3niU33zkkqDY20KRumt4kyIFWOoWJCFw1mtfl2I7UKSQtYjfQNz1O1IJuTm5aHalSMWy1gTEXPqOtCnWuBWpWIaMZcGOx+OeVdXmMxWpexfAK+9KFdqtgmHDqrgDUKxWzA61D59ZthtwdiH94eLfvyM9CwPInhoB6kXz2jgy3QLX2kRm8c126lwpbyL/BV4Bqn+ARNmEAAAAInRFWHRjb21tZW50AFJlbmRlcmVkIGJ5IFF1aWNrTGFUZVguY29tIEnQtgAAACV0RVh0ZGF0ZTpjcmVhdGUAMjAyMi0xMi0wMlQxNzoyMzozOCswOTowMCfwVEQAAAAldEVYdGRhdGU6bW9kaWZ5ADIwMjItMTItMDJUMTc6MjM6MzgrMDk6MDBWrez4AAAAAElFTkSuQmCC) . 
Each mesh face is a triangle so consists of three vertices, these can be obtained using the face vertex arrays: `(V[F1[n], V[F2[n], V[F3[n]`.

 ## Methods
List of methods associated with the mesh object.
- <font face="consolas"> <font color="orange">scene_obj</font> getObj( <font color="green">num</font> obj )</font> 
	>Returns the scene object with global object id `obj`
- <font face="consolas"> <font color="blue">vec3</font> getObjProp( <font color="orange">scene_obj</font> obj, <font color="purple">enum</font> prop )</font>
	>Returns the requested property `prop` of scene object `obj`. `prop` must be an object property enum.
	>All values are returned as a vec3, values that are not vectors are still returned as vec3 but can be used in indexing.

#### Internal methods
- <font face="consolas"> <font color="red">INTERNAL</font> <font color="blue">vec3</font> getObjPos( <font color="green">num</font> ptr )</font>
- <font face="consolas"> <font color="red">INTERNAL</font> <font color="blue">vec3</font> getObjRot( <font color="green">num</font> ptr )</font>
- <font face="consolas"> <font color="red">INTERNAL</font> <font color="blue">vec3</font> getObjScale( <font color="green">num</font> ptr )</font>