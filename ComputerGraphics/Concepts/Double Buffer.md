## **Quick Summary**

Double buffering is a rendering technique that uses two frame buffers so a new frame can be fully rendered before being displayed, preventing flickering and partially drawn images.

---

## **Core Idea**

* Rendering occurs in a hidden buffer while another buffer is currently displayed.
* When rendering finishes, the buffers are swapped, instantly showing the completed frame.
* This prevents the display from showing incomplete drawing operations.
* The technique separates drawing operations from display output.

---

## **What it is**

Double buffering is a graphics technique that uses two frame buffers to ensure smooth visual updates during rendering.

If a system draws directly to the screen buffer while it is being displayed, the display may show partially drawn frames. This happens because rendering can take longer than the screen refresh cycle.

Double buffering solves this by using two buffers:

* **Front Buffer** – the image currently displayed on the screen.
* **Back Buffer** – the buffer where the next frame is rendered.

Once rendering finishes, the buffers swap roles, making the completed frame visible instantly.

This ensures the user only sees fully rendered frames, eliminating visual artifacts caused by incomplete rendering.

---

## **How its Used**

### Real-Time Graphics

Games and interactive applications use double buffering to ensure smooth frame updates.

### GPU Rendering Pipelines

Modern graphics APIs render frames into back buffers managed by the GPU before presenting them.

### User Interface Systems

Windowing systems and UI frameworks use double buffering to prevent flicker when redrawing windows.

### Graphics APIs

Many rendering systems implement double buffering internally, including [[OpenGL]] and game engines.

---

## **Example**

### Example 1: Frame Rendering Cycle
```
Frame 1
Front Buffer -> Displayed on screen
Back Buffer  -> Rendering next frame
```

After rendering finishes:
```
Buffer Swap
Back Buffer  → becomes Front Buffer
Front Buffer → becomes Back Buffer
```

Now the completed frame appears instantly.

### Example 2: Without Double Buffering

If drawing occurs directly to the display buffer:

* A triangle might appear half drawn
* Objects may pop in gradually
* The screen may flicker between updates

Double buffering prevents this by ensuring only finished frames are shown.

---

## **Details**

### Buffer Swap

The swap operation exchanges which buffer is displayed and which is used for rendering. This operation is often called buffer flipping or page flipping.

### Relation to Screen Refresh

Displays refresh at fixed intervals (for example 60 Hz). Double buffering ensures the display always reads from a stable completed frame.

### Extension: Triple Buffering

Some systems use triple buffering, which adds a third buffer to allow rendering to continue even if the display has not finished using the previous frame.

### Hardware Support

Modern GPUs implement double buffering as part of the graphics pipeline and swap chain systems used by graphics APIs.

---

## **Related**

* [[Frame Buffer]]
* [[Rasterization]]
* [[OpenGL]]
* [[Rendering Pipeline]]
* [[VSync]]

---

## **One Line Recall**

Double buffering prevents flickering by rendering frames in a back buffer and swapping it with the front buffer once rendering is complete.