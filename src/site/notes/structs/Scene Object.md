---
{"dg-publish":true,"permalink":"/structs/scene-object/"}
---

# Scene object 🎭
This is what is placed in a scene to be rendered.


## Constructor
A scene object consists of an array with the following entries (by index):

| index | Name | Description | 
| --- | --- | --- | 
| 1 | Position pointer | Pointer into scene object position array |
| 2 | Rotation pointer | Pointer into scene object rotation array |
| 3 | Scale pointer | Pointer into scene object scale array |
| 4 | Mesh index | Global mesh index that object uses |
| 5 | Material index | Global material index that object uses |

 ## Methods
List of methods associated with the scene object.
- <font face="consolas"> <font color="orange">scene_obj</font> getObj( <font color="green">num</font> obj )</font> 
	>Returns the scene object with global object id `obj`
- <font face="consolas"> <font color="blue">vec3</font> getObjProp( <font color="orange">scene_obj</font> obj, <font color="purple">enum</font> prop )</font>
	>Returns the requested property `prop` of scene object `obj`. `prop` must be an object property enum.
	>All values are returned as a vec3, values that are not vectors are still returned as vec3 but can be used in indexing.

#### Internal methods
- <font face="consolas"> <font color="red">INTERNAL</font> <font color="blue">vec3</font> getObjPos( <font color="green">num</font> ptr )</font>
- <font face="consolas"> <font color="red">INTERNAL</font> <font color="blue">vec3</font> getObjRot( <font color="green">num</font> ptr )</font>
- <font face="consolas"> <font color="red">INTERNAL</font> <font color="blue">vec3</font> getObjScale( <font color="green">num</font> ptr )</font>