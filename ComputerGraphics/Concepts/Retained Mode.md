Used by: [[WPF]], [[SVG]], most game engines

**Definition:**
Graphics programming model where the system (Graphics library or framework) **stores and manages the scene for you**, instead of requiring you to redraw everything manually each frame

**Core Idea**
Describe what objects exist (shapes, images, UI elements), the framework:
- Keeps them in memory (often in a [[Scene Graph]])
- tracks properties (pos, scale, color, etc..)
- Automatically redraws when needed
- Handles optimizations internally

ex: If the window moves, resizes, or updates, the system redraws the shape automatically

only update properties