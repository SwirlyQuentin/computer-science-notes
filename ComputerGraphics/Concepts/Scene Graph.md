**Definition**:
A scene graph is a **hierarchical tree structure** used in [[Retained Mode]] graphics systems to organize and manage all objects in a scene.

### **Core Idea**
Instead of storing objects randomly, the system organizes them in a **parent-child tree structure**

Each node can represent:
- Shape
- Transformation
- Light
- Camera
- A group of objects

### **Why It's Useful**
It's ***hierarchical***
- Transformations applied to parent automatically apply to children
- Makes grouping objects easier
- Improves rendering efficiency
- Simplifies animation and organization

### **Example**

```
Car (parent)
 ├── Body
 ├── Wheel_FL
 ├── Wheel_FR
 ├── Wheel_BL
 └── Wheel_BR
```

Moving car moves both the body and all wheels

### **Where Scene Graphs are used**
[[WPF]]
Unity
[[SVG]]
