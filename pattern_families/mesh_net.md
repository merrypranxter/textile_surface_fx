# Mesh / Net

Uniform grid. Open grid.

## What It Is

Mesh or net is a **fabric with uniform, regular holes** created by looping, knotting, or weaving threads into a grid structure. It's used for sportswear, bags, and layering.

## Construction

- **Grid structure**: Regular, even spacing of holes
- **Various methods**: Knitted, woven, or knotted
- **Stretch or rigid**: Can be elastic or stiff
- **Synthetic common**: Often polyester or nylon

## Visual DNA

- **Uniform holes**: Regular grid pattern
- **Grid lines**: Visible connecting threads
- **See-through**: Transparent or semi-transparent
- **Sporty or utilitarian**: Functional rather than decorative
- **Common uses**: Sportswear, bags, layering, screens, filters

## Shader Parameters

| Parameter | Range | Notes |
|-----------|-------|-------|
| `grid_size` | 0.005–0.02 | Hole dimensions |
| `hole_shape` | square/hex/round | Grid geometry |
| `line_thickness` | 0.001–0.005 | Connecting thread width |
| `transparency` | 0.5–0.95 | See-through amount |

## GLSL Snippet

```glsl
float mesh(vec2 uv, float size) {
    float grid = square_grid(uv, size);
    float holes = 1.0 - grid;
    float lines = grid * line_thickness;
    return holes + lines;
}
```

## Prompt Template

> "Mesh fabric in [COLOR], uniform [SHAPE] grid with regular holes, sporty see-through textile, synthetic net structure"

## Anti-Drift

- **Not lace**: Mesh is uniform grid; lace is decorative openwork
- **Not tulle**: Tulle is a specific fine mesh; mesh is general category
- **Utilitarian**: Usually functional, not decorative

---

*Grid, hole, grid, hole. The regularity is the structure.*
