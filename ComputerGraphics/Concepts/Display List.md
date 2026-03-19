---
aliases:
  - Display Lists
---

## **Quick Summary**

A display list stores rendering commands directly on the GPU so they can be executed quickly.

---

## **Core Idea**

Instead of sending geometry every frame, the commands are **compiled once and stored on the GPU**, allowing fast repeated rendering.

---

## **What it is**

A **Display List** is an OpenGL feature that stores a sequence of rendering commands in GPU memory.

The commands are **compiled once** and then reused whenever the object is drawn.

This reduces the amount of data sent from the CPU to the GPU.

However, display lists have a major limitation:

* their contents **cannot be modified dynamically**

Because of this limitation, display lists are mostly replaced by **VBOs in modern graphics programming**.

---

## **How its Used**

Display lists were used when rendering **static geometry**, such as:

* terrain
* static objects
* environment geometry

Workflow:

1. Create display list
2. Record drawing commands
3. Execute the list when rendering

---

## **Example**

Creating a display list:
```
GLuint list = glGenLists(1);

glNewList(list, GL_COMPILE);

glBegin(GL_TRIANGLES);
glVertex3f(0,0,0);
glVertex3f(1,0,0);
glVertex3f(0,1,0);
glEnd();

glEndList();
```

Rendering:
```
glCallList(list);
```

The GPU executes the stored commands.

---

## **Details**

**Advantages**
* very fast rendering
* minimal CPU overhead
* commands stored on GPU

**Disadvantages**
* cannot modify vertex data dynamically
* deprecated in modern OpenGL

Modern engines prefer **VBOs**.

---

## **Related**

* [[Vertex Buffer Object (VBO)]]
* [[Vertex Array]]
* [[Immediate Mode]]

---

## **One Line Recall**

A **display list** stores compiled rendering commands on the GPU for fast execution.