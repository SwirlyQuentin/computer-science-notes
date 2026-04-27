```cpp
#include <glad/glad.h>
#include <GLFW/glfw3.h>
#include <iostream>

int main() {
    if (!glfwInit()) {
        std::cout << "Failed to init GLFW\n";
        return -1;
    }

    GLFWwindow* window = glfwCreateWindow(800, 600, "Terrain", nullptr, nullptr);
    if (!window) {
        std::cout << "Failed to create window\n";
        glfwTerminate();
        return -1;
    }

    glfwMakeContextCurrent(window);

    if (!gladLoadGLLoader((GLADloadproc)glfwGetProcAddress)) {
        std::cout << "Failed to init GLAD\n";
        return -1;
    }

    while (!glfwWindowShouldClose(window)) {
        glfwPollEvents();
        glfwSwapBuffers(window);
    }

    glfwTerminate();
    return 0;
}
```

## 1. Includes
```
#include <glad/glad.h>
#include <GLFW/glfw3.h>
#include <iostream>
```

Including the libraries needed in the file


## 2. Initialize GLFW
```cpp
if (!glfwInit()) {
    std::cout << "Failed to init GLFW\n";
    return -1;
}
```

- `glfwInit()` sets up the library
- If this fails, the program stops execution


## 3. Create a Window
```cpp
GLFWwindow* window = glfwCreateWindow(800, 600, "Terrain", nullptr, nullptr);
    if (!window) {
        std::cout << "Failed to create window\n";
        glfwTerminate();
        return -1;
    }
```

- Creates window of size 800x600 titles "Terrain"
- Returns pointer to a GLFWwindow

If fails, program stops execution


## 4. Make OpenGL Context Current
```cpp
glfwMakeContextCurrent(window);
```
- Tells OpenGL that all rendering commands now apply to this window
- Without this OpenGL calls wont know where to render


## 5. Initialize GLAD

```cpp
if (!gladLoadGLLoader((GLADloadproc)glfwGetProcAddress)) {
    std::cout << "Failed to init GLAD\n";
    return -1;
}
```

- OpenGL functions are not directly available 
- This loads them at runtime
- Without this `gladLoadGLLoader((GLADloadproc)glfwGetProcAddress` you cannot use OpenGL


## 6. Main Loop
```cpp
while (!glfwWindowShouldClose(window)) {
    glfwPollEvents();
    glfwSwapBuffers(window);
}
```

- This is the main render/game loop 
- Inside the loop:
	- Handle Input/events
		- Keyboard Input
		- Mouse movement
		- Window Events
	- Swaps Buffers
		- [[Double Buffer]]


## 7. Cleanup
```
glfwTerminate();
return 0;
```

- Frees GLFW resources
- Ends program