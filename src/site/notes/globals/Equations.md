---
{"dg-publish":true,"permalink":"/globals/equations/"}
---

# Equations/Functions
These are useful equations that come stock with the Kenos engine. Equations that start with capital letters are regular mathematical operations, usually in vector math or linear algebra. 

Equations and functions may have special keywords that help define what they do:
- <font face="consolas"><font color="green">num</font>, <font color="blue">vec3</font>, <font color="yellow">pnt</font></font>  define different data types: number, 3d-vector (array with 3 elements), or point. Arrays are denoted by square brackets after type declaration. Some structs can be used as types, and this is usually handled by having an array with each index represent a different property such as a [[structs/Scene Object\|Scene Object]].
- <font face="consolas"><font color="red">DEPRECATED</font></font> means a function is deprecated and is no longer in use, or should no longer be in use.
- <font face="consolas"><font color="red">INTERNAL</font></font> means a function is internal and should not be called by itself. Usually used for helper functions.
- <font face="consolas"><font color="orange">private</font></font> means this is a locally scoped variable and will not function outside of its intended scope. This is equivalent to the internal flag but cannot be used outside of the designated scope at all.


#### Vector equations
- <font face="consolas"> <font color="green">num</font> Dot( <font color="blue">vec3</font> a, <font color="blue">vec3</font> b )</font>
- <font face="consolas"> <font color="blue">vec3</font> Cross( <font color="blue">vec3</font> a, <font color="blue">vec3</font> b )</font>
- <font face="consolas"> <font color="green">num</font> Dist( <font color="blue">vec3</font> a, <font color="blue">vec3</font> b )</font>
	>Distance between a and b
- <font face="consolas"> <font color="blue">vec3</font> Unit( <font color="blue">vec3</font> a )</font>
	>Returns normalized unit vector of a
- <font face="consolas"> <font color="blue">vec3</font> Normal( <font color="blue">vec3</font> a, <font color="blue">vec3</font> b, <font color="blue">vec3</font> c )</font>
	>Returns the normal of the plane described by vectors `a`, `b`, and `c`

#### Screen functions
- <font face="consolas"><font color="red">DEPRECATED</font> <font color="yellow">pnt[]</font> getScrnPxl( <font color="green">num</font> n )</font>
	>Returns screen pixel n. Deprecated, use `getScrnPxls` and index it.
- <font face="consolas"><font color="yellow">pnt[]</font> getScrnPxls(  )</font>
	>Returns screen pixel coordinates to be used as point D in ray casting stage.

#### Baryocentric coordinate equations
- <font face="consolas"> <font color="green">num</font> isIn( <font color="blue">vec3</font> a, <font color="blue">vec3</font> b, <font color="blue">vec3</font> c, <font color="blue">vec3</font> p )</font>
	>Returns 1 if vector `p` is contained withing triangle defined by `a`, `b`, `c`. Note that all of the vectors must be coplanar or this will perform unexpectadly.
- <font face="consolas"><font color="red">INTERNAL</font> <font color="green">num</font> getBarU( <font color="blue">vec3</font> v0, <font color="blue">vec3</font> v1, <font color="blue">vec3</font> v2 )</font>
- <font face="consolas"><font color="red">INTERNAL</font> <font color="green">num</font> getBarV( <font color="blue">vec3</font> v0, <font color="blue">vec3</font> v1, <font color="blue">vec3</font> v2 )</font>
	>Used in baryocentric coordinate calculation, in `isIn` equation.

#### Parametric to cartesian converter functions
All of these ar deprecated, will likely be removed. These converted parametric value `t` to cartesian coordinates. `i` is index of which screen point the casted ray belonged to.
- <font face="consolas"><font color="red">DEPRECATED</font> <font color="green">num</font> interToCartX( <font color="blue">num</font> i, <font color="blue">num</font> t )</font>
- <font face="consolas"><font color="red">DEPRECATED</font> <font color="green">num</font> interToCartY( <font color="blue">num</font> i, <font color="blue">num</font> t )</font>
- <font face="consolas"><font color="red">DEPRECATED</font> <font color="green">num</font> interToCartZ( <font color="blue">num</font> i, <font color="blue">num</font> t )</font>

#### Array functions
- <font face="consolas"> <font color="green">num</font> posMin( <font color="green">num[]</font> arr )</font>
- <font face="consolas"> <font color="green">num</font> posMax( <font color="green">num[]</font> arr )</font>
	>Returns the index of the min and max entry in `arr` respectivly.
- <font face="consolas"> <font color="green">num[]</font> flatten( <font color="green">num[]</font> arr )</font>
	>Flatten `arr` into the range 0 -> 1.

#### Ray-plane intersection equations
- <font face="consolas"> <font color="green">num</font> intersect( <font color="blue">vec3</font> a, <font color="blue">vec3</font> b, <font color="blue">vec3</font> c, <font color="blue">vec3</font> d, <font color="blue">vec3</font> e )</font>
	>Returns the t value for the intersection of the a plane representd by vectors `a`, `b`, `c` and the parametric ray passing through `d` and `e`.
- <font face="consolas"> <font color="red">INTERNAL</font> <font color="orange">private</font> <font color="blue">vec3</font> normPln</font>
	>Contains the normal vector of the plane, used in `intersect` equation
- <font face="consolas"> <font color="red">INTERNAL</font> <font color="green">num</font> interPln( <font color="green">num</font> x, <font color="green">num</font> y, <font color="green">num</font> z )</font>
- <font face="consolas"> <font color="red">INTERNAL</font> <font color="orange">private</font> <font color="green">num</font> kpln</font>