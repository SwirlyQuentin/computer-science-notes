### **Concept**

Given a mathematical line, find the appropriate pixels to light up in order to display a discrete line closest to the one given

At each step of the line, the program needs to choose between two candidate pixels to light up
- It tests which pixel is closer to the line by evaluating the line equation at the **Midpoint between them**

We use a decision function to determine which pixel is closer

### **Walkthrough**

Given line segment from (x0, y0) to rightmost (x1, y1)

y = mx + b
m = dy/dx = (y1 - y0) / (x1 - x0)

**Assuming 0 <= m <= 1**

Start at the leftmost edge of the line and move right one pixel at a time
Illuminating either the pixel to the **East** or **NorthEast**

---
We can rewrite y = mx + b as **F(x, y) = ax + by + c = 0**
- This tells whether the point (x, y) is 
	- Above the line - F(x, y) < 0
	- Below the line - F(x, y) > 0
	- On the line - F(x, y) = 0

Steps:
y = (dy/dx)x + b
0 = (dy/dx)x - y + b
- Multiply both sides by dx to get rid of fraction
0 = dy x - dx y + dx b

F(x, y) = dy x - dx y + dx b

---

Given we have illuminated the pixel at (xp, yp) we nex illuminate either:
- Pixel to the **East** (xp + 1, yp)
- Pixel to the **NorthEast** (xp + 1, yp + 1)

#### **TO DECIDE:**

We look at the **Midpoint** between East and Northeast pixel and see which side of the midpoint the line falls on

- Line above - Illuminate **NORTHEAST** pixel
- Line below - Illuminate **EAST** pixel
- Line on midpoint - CHOOSE to illuminate the **EAST** pixel

To decide we create a **decision variable d** 

d = F(xp + 1, yp + 0.5) -> Midpoint between candidate pixels

- **d > 0** -> pick **NORTHEAST** pixel
- **d < 0** -> pick **EAST** pixel
- **d = 0** -> *CHOOSE* to pick **EAST** pixel

This gives us the pixel to illuminate but how do we get the next one?

---

#### **Getting the Next Decision Value**

##### If **East** is chosen:
---
The **new** midpoint is incremented by 1 in x, 0 in y
(x + 1, y)

We want to compute the new d without recomputing the formula:

dCurrent = F(xp + 1, y + 0.5)

**USING** F(x, y) = dy x - dx y + dx b | we can **expand** to:

dCurrent = dy(xp + 1) - dx(y + 0.5) + dx b

When considering East was chosen:
the **new d** would be
dNew = F(xp + 2, yp + 0.5)
dNew = dy(xp + 2) - dx(yp + 0.5) + dx b

Now when finding the difference between these two:
dNew - dCurrent

dy(xp + 2) - dx(yp + 0.5) + dx b - (dy(xp + 1) - dx(y + 0.5) + dx b)

= dy
dE = dy

So when choosing **EAST**, incrementing **d** by **dy** gives the decision variable at the next midpoint

dnew = dcurrent + dy



##### **If Northeast is Chosen:**
---
The **new** midpoint is incremented by 1 in x, 1 in y
(x + 1, y + 1)

We want to compute the new d without recomputing the formula:

dCurrent = F(xp + 1, y + 0.5)

**USING** F(x, y) = dy x - dx y + dx b | we can **expand** to:

dCurrent = dy(xp + 1) - dx(y + 0.5) + dx b

When considering Northeast was chosen:
the **new d** would be
dNew = F(xp + 2, yp + 1.5)
dNew = dy(xp + 2) - dx(yp + 1.5) + dx b

Now when finding the difference between these two:
dNew - dCurrent

dy(xp + 2) - dx(yp + 0.5) + dx b - (dy(xp + 1) - dx(y + 1.5) + dx b)

= dy - dx
dNE = dy - dx

So when choosing **NORTHEAST**, incrementing **d** by **dy - dx** gives the decision variable at the next midpoint

dnew = dcurrent + (dy - dx)


#### **Initial Values + Getting Rid of the 0.5**

The initial point (x0, y0) is known
so..
initial d = F(x0 + 1, y0 + 0.5)

**USING** F(x, y) = dy x - dx y + dx b | we can **expand** to:

initial
d = F(x0, y0) = dy(x0 + 1) - dx(y0 + 0.5) + dx b
d = F(x0, y0) = (dy x0 - dx y0 + dx b) + dy - 0.5 dx
d = F(x0, y0) + dy - 0.5 dx

Since (x0, y0) is on the line, F(x0, y0) = 0

d = dy - 0.5 dx

The division by 2 is annoying 
- Changes entire expression to have floats
- Floats are slow when it comes to math

>We can avoid the division by multiplying F() by 2

This **does not** change anything as we only need to know if d < 0, = 0, or > 0
*Multiplication does not change anything*

With this however we need to change everything to include the x2:

d = 2dy - dx
dE = 2dy
dNE = 2(dy - dx)

#### **Full Algorithm**:

```
dx = x1 - x0  
dy = y1 - y0  
d = dy * 2 - dx  
dE = dY * 2  
dNE = (dy - dx) * 2  
X = x0  
Y = y0  
illuminate x, y

while (x < x1) repeatedly

if ( d <= 0)

add dE to d  
add 1 to x  

else

add dNE to d  
add 1 to x  
add 1 to y  

illuminate x, y
```

# **!!!! EXCEPTION:**

>This **ONLY** works in one octant

To make it work in all octants, if statements can be added to change the initial values to get the same result

**HOWEVER**

A cleaner version can be used that works for all octants

```
int dx = Math.abs(x1 - x0);
int sx = (x0 < x1) ? 1 : -1;
int dy = -Math.abs(y1 - y0);
int sy = (y0 < y1) ? 1 : -1;
int err = dx + dy;

glBegin(GL_POINTS);
while (true) {
	glVertex2f(x0, y0);
	  
	if (x0 == x1 && y0 == y1) {
		break;
	}
	  
	int e2 = 2 * err;
	if (e2 >= dy) {
		err += dy;
		x0 += sx;
	}
	if (e2 <= dx) {
		err += dx;
		y0 += sy;
	}
}
glEnd();
```

#### **Key Differences**

- The use of sy and sx make it so whichever way the slope goes, the line always advances correctly when adding to it
- d has now become err which works somewhat like d, deciding whether to move or not in x and y directions
- err is essentially |dx| - |dy|
- err keeps track of how far away we are from the line
	- if the error is smaller that the change in y we move in the x direction and subtract dy
		- remember in the actual code dy is always negative so in the code this is opposite
	- if the error is smaller than the change in x we move in the y direction and add dx
- We multiply by 2 because of the initial /2


# **Example**

Line from:

(2,2) → (7,5)

---

## Setup

dx = |7 - 2| = 5  
dy = -|5 - 2| = -3  

sx = 1  
sy = 1  

err = dx + dy = 5 + (-3) = 2  

---

## Iterations

### (2,2)
err = 2  
e2 = 4  

4 ≥ -3 → move x → err = 2 - 3 = -1  
4 ≤ 5  → move y → err = -1 + 5 = 4  

New point: (3,3)

---

### (3,3)
err = 4  
e2 = 8  

8 ≥ -3 → move x → err = 4 - 3 = 1  
8 ≤ 5  → false  

New point: (4,3)

---

### (4,3)
err = 1  
e2 = 2  

2 ≥ -3 → move x → err = 1 - 3 = -2  
2 ≤ 5  → move y → err = -2 + 5 = 3  

New point: (5,4)

---

### (5,4)
err = 3  
e2 = 6  

6 ≥ -3 → move x → err = 3 - 3 = 0  
6 ≤ 5  → false  

New point: (6,4)

---

### (6,4)
err = 0  
e2 = 0  

0 ≥ -3 → move x → err = 0 - 3 = -3  
0 ≤ 5  → move y → err = -3 + 5 = 2  

New point: (7,5)

---

## Final Pixels

(2,2)  
(3,3)  
(4,3)  
(5,4)  
(6,4)  
(7,5)