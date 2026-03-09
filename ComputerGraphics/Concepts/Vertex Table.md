## Quick Summary
A vertex table is a structured list of per-vertex data (position plus attributes). It is the main geometry input used by rendering pipelines before primitives are assembled.

## What It Is
A vertex table stores one vertex per row. Each row may contain:
- Position `(x, y, z)`
- Normal `(nx, ny, nz)`
- Texture coordinates `(u, v)`
- Color `(r, g, b, a)`
- Tangent/bitangent
- Skinning data (weights and bone indices)

Think of it as an attribute database for vertices.

## How It Is Used
- Vertex processing: shaders read each vertex row.
- Primitive assembly: indices reference rows to build triangles/lines.
- [[Interpolation]] source: rasterization interpolates per-vertex attributes across fragments.
- Animation: skinned meshes update transformed vertex positions from this data.

## Vertex Table + Index Buffer
- Vertex table: unique vertex attributes.
- Index buffer: integer references that define topology.

This avoids duplicating shared corners.

## Mini Example
Vertex rows:
- `v0 = pos(0,0,0), uv(0,0)`
- `v1 = pos(1,0,0), uv(1,0)`
- `v2 = pos(1,1,0), uv(1,1)`
- `v3 = pos(0,1,0), uv(0,1)`

Indices:
- `(0,1,2)`
- `(0,2,3)`

Result: one quad rendered using two triangles.

## Practical Design Choices
- Interleaved layout vs separate attribute arrays.
- Precision choice: float32/float16/packed formats.
- Data alignment for GPU-friendly access.

## Common Pitfalls
- Attribute layout mismatch with shader inputs.
- Inconsistent winding causes culling or normal issues.
- Duplicate near-identical vertices waste memory.

## Exam-Style Questions
1. Why does indexed rendering reduce memory cost?
2. What is the difference between geometry data and topology data?
3. How can a bad vertex layout break shading?

## One-Line Recall
A vertex table stores what each vertex is; indices decide how vertices connect into renderable primitives.
