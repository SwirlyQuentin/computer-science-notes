## Quick Summary
Interpolation estimates values between known samples by constructing a function that matches those samples exactly.

## What It Is
Given sample points `(x_i, y_i)`, interpolation builds `f(x)` so that:
- `f(x_i) = y_i` for each sample.

It answers: "what value should be between known values?"

## How It Is Used
- Color/attribute interpolation across triangles.
- Texture coordinate interpolation per fragment.
- Keyframe animation blending.
- Image scaling and signal resampling.

## Common Methods
- Nearest neighbor: fastest, blocky results.
- Linear: simple and common.
- Polynomial: exact fit through many points, risk of oscillation.
- [[Spline]]: smooth piecewise interpolation.

## Interpolation vs Approximation
- Interpolation: must pass through samples.
- Approximation: follows trend but may miss exact sample values.

## Practical Notes
- Method choice depends on speed vs smoothness needs.
- Sample spacing affects error.
- Boundary handling often creates visible artifacts if done poorly.

## Exam-Style Questions
1. What is the main requirement that defines interpolation?
2. Why can high-degree polynomial interpolation be unstable?
3. In graphics, where is [[linear interpolation]] used constantly?

## One-Line Recall
Interpolation fills in unknown values between known samples while preserving sample values exactly.