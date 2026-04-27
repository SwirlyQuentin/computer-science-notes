```cmake
cmake_minimum_required(VERSION 3.10)
project(Terrain)
  
set(CMAKE_CXX_STANDARD 17)

add_library(glad src/glad.c)

find_package(glfw3 REQUIRED)

include_directories(include libs/glad/include)

add_executable(Terrain
src/main.cpp
) 

target_link_libraries(Terrain
glfw
glad
"-framework OpenGL"
)
```

### 1. `cmake_minimum_required(VERSION 3.10)`
- Defines the minimum required version to run the project
- doesn't even try if its not at least version 3.10

This prevents weird compatibility issues + locks in behavior of commands

### 2. `project(Terrain)`

- Defines the project

This name is used for:
- Default executable naming
- Internal CMake variables

### 3. `set(CMAKE_CXX_STANDARD 17)`

- Forces the compiler to use C++17

Without this line could result in compiler using an older version

### 4. `add_library(glad src/glad.c)`

- Compiles glad.c into a reusable library called glad

This:
- Keeps GLAD separate from the main executable
- Lets it be linked in cleanly later
- Avoids recompiling it multiple times if resued

### 5. `find_package(glfw3 REQUIRED)`

- Finds GLFW on the system
- Located headers + compiled library
- Makes available for linking

### 6. `include_directories(include libs/glad/include)`

- Tells where to look for headers

Without this:
`#include <glad/glad.h>` would fail


### 7. 
```
add_executable(Terrain
    src/main.cpp
)
```

- Determines the final program that is run
- **This is where more .cpp files are added**


### 8. 
```
target_link_libraries(Terrain
    glfw
    glad
    "-framework OpenGL"
)
```

- Links these together

"-framework OpenGL"
- Mac specific way to link OpenGL
- On MacOS, OpenGL is a framework not normal .lib