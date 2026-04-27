# **OpenGL**
**Role:** The graphics api, talks directly to the GPU

**Used For:**

- Sending vertex data (The terrain mesh) to the GPU
- Running shaders (vertex + fragment)
- Drawing the terrain

**Core concepts:**
- [[Vertex Buffer Object (VBO)|VBO]]
- [[VAO]] (Vertex Array Object)
- Shaders
- Draw Calls

# **GLFW**
**Role:** Window + input + context creation, It deals with creating and managing the window

**Used For:**

- Creating the Window
- Creating the OpenGL context
- Handling keyboard/mouse input
- Game loop timing

```cpp
glfwCreateWindow(...)
glfwPollEvents()
glfwSwapBuffers(window)
```

GLFW does not render anything, it just gives a place to render


# **GLAD**
**Role:** OpenGL function loader, connects functions from opengl to cpp

**Used For:**
- Loads function pointers fr OpenGL at runtime
- C++ doesnt know modern OpenGL functions by default

Only done once:
```cpp
gladLoadGLLoader((GLADloadproc)glfwGetProcAddress);
```

# **GLM**
**Role:** Math library that deals with math useful in OpenGL

**Used For:**
- Vectors (`vec3`, `vec2`)
- Matrices (transformations)
- Camera math
- Projection/view matrices

**Ex:**
```
glm::vec3 position;
glm::mat4 projection;
```
