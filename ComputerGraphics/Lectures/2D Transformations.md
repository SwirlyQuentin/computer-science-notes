

### **How are Geometric Transformations Used**

- At the lowest level, objects are a collection of vertices
- objects have location, orientation, size
- Correspond to transformations: Translation, Rotation, and Scaling

### **Linear Algebra Concepts**

- 3D coordinate geometry
- Vectors in 2D and 3D space
- Dot product and Cross product
- Vector and matrix notation and algebra
- Identity matrix
- Multiplicative associativity
- Matrix Transpose and Inverse
- Homogeneous coordinates


### **Vectors**

Vectors are represented by ****bold-italic letters (v)***

any vector in a plane can be defined as the sum of two non collinear basis vectors

- A basis for vector space is a set of vectors with these properties:
	- V in set are linearly independent
	- Any v can be expressed as a linear combination of the basis vectors
- Multiplying vector by scalar increases mag.

### **Linear Transformations**
- Transformations of points around the origin
	- will result in another point in the same coordinate system **transformed about the origin**
	- **INCLUDES** Scaling and Rotation
	- **DOES NOT INCLUDE** Translation (moves the origin)

#### **Transformations as Matrices**

- Linear transformations can be represented as matrices

$$
T = 
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix}
$$
- A transformation of vector x
$$
x = 
\begin {bmatrix}
x_1 \\
x_2
\end {bmatrix}
$$

has the form:


$$
T
\begin {bmatrix}
x_1 \\
x_2
\end {bmatrix}
=
\begin {bmatrix}
a & b \\
c & d
\end {bmatrix}
\begin {bmatrix}
x_1 \\
x_2
\end {bmatrix}
=
\begin {bmatrix}
ax_1 + bx_2\\
cx_2 + dx_2
\end {bmatrix}
$$
Now let e1 and e2 be the standard basis vectors:

$$
e1 =
\begin {bmatrix}
1 \\
0
\end {bmatrix}
,\;
e2 =
\begin {bmatrix}
0 \\
1
\end {bmatrix}
$$
Substitute each basis vector for x:
$$
T
\begin {bmatrix}
1 \\
0
\end {bmatrix}
=
\begin {bmatrix}
a & b \\
c & d
\end {bmatrix}
\begin {bmatrix}
1 \\
0
\end {bmatrix}
=
\begin {bmatrix}
a \\
c
\end {bmatrix}
$$
**and**
$$
T
\begin {bmatrix}
0 \\
1
\end {bmatrix}
=
\begin {bmatrix}
a & b \\
c & d
\end {bmatrix}
\begin {bmatrix}
0 \\
1
\end {bmatrix}
=
\begin {bmatrix}
b \\
d
\end {bmatrix}
$$
Therefore:
$$
T(e_1) =
\begin {bmatrix}
a \\
c
\end {bmatrix}
\quad
T(e_2)=
\begin {bmatrix}
b \\
d
\end {bmatrix}
$$

This gives a strategy for deriving transformation matrices


### **Scaling**

In order to scale **x** by c1 and **y** by c2:

$$
v =
\begin {bmatrix}
x \\
y
\end {bmatrix}
;
\quad
v' = 
\begin {bmatrix}
x' \\
y'
\end {bmatrix}
$$

v - The original vector
v' - The new transformed vector

**v' = Sv**

Derive **S** by determining how **e1** and **e2** should be transformed

**Scale in x by Sx**
$$
e_1=
\begin {bmatrix}
1 \\
0
\end {bmatrix}
\quad
->
\quad
s_x*e_1=
\begin {bmatrix}
s_x \\
0
\end {bmatrix}
$$

**Scale in y by Sy**

$$
e_2=
\begin {bmatrix}
0 \\
1
\end {bmatrix}
\quad
->
\quad
s_y*e_2=
\begin {bmatrix}
0 \\
s_y
\end {bmatrix}
$$
Thus:
$$
\begin {bmatrix}
s_x & 0 \\
0 & s_y
\end {bmatrix}
$$

Ex:
v (2, 1) scaled by S(3, 2) = v'(6, 2)

**Things to note:**
- Does not preserve angles between lines (except when scaling is uniform, ie: sx = sy)


### **Rotation**

Rotate by θ about the origin
**v' = Sv**

Derive Rθ from e1 and e2

**First Column of R**

$$
e_1=
\begin {bmatrix}
1 \\
0 
\end {bmatrix}
\quad
->
\begin {bmatrix}
cosθ\\
sinθ
\end {bmatrix}
$$

**Second Column of R**

$$
e_1=
\begin {bmatrix}
0 \\
1 
\end {bmatrix}
\quad
->
\begin {bmatrix}
-sinθ\\
cosθ
\end {bmatrix}
$$

**Therefore:**

$$
R_θ=
\begin {bmatrix}
cosθ & -sinθ \\
sinθ & cosθ 
\end {bmatrix}
$$

So now taking Rθ we can transform **v**

$$
R_θ*v=
\begin {bmatrix}
cosθ & -sinθ \\
sinθ & cosθ 
\end {bmatrix}
\begin {bmatrix}
x \\
y 
\end {bmatrix}
=
\begin {bmatrix}
xcosθ - ysinθ \\
xsinθ + ycosθ 
\end {bmatrix}
=
\begin {bmatrix}
x'\\
y'
\end {bmatrix}
=v'
$$

In the end:
x' = xcos(θ) - ysin(θ)
y' = xsin(θ) + ycos(θ)

**Other Properties of Rotation**
- Preserves lengths in objects and angles between parts of objects


### **Translation**
