# Corduroy

Ridged pile. Wale lines.

## What It Is

Corduroy is a **fabric with raised vertical ridges (wales)** created by weaving extra warp threads that are cut to form piles in distinct rows. The width of the wales varies from fine needlecord to wide jumbo.

## Construction

- **Wale weaving**: Extra warp threads in specific rows
- **Cut pile**: Pile cut to create ridges
- **Wale spacing**: Distance between ridges determines cord width
- **Nap direction**: Pile lies along the wale

## Visual DNA

- **Vertical ridges**: Parallel raised lines across fabric
- **Wale width**: Fine (21 wales/inch) to jumbo (3 wales/inch)
- **Light channels**: Shadows between ridges create depth
- **Soft ridges**: Pile compresses when touched
- **Common uses**: Trousers, jackets, upholstery, children's clothing

## Shader Parameters

| Parameter | Range | Notes |
|-----------|-------|-------|
| `wale_count` | 3–21 | Ridges per inch |
| `ridge_height` | 0.005–0.02 | Pile height |
| `valley_depth` | 0.0–0.01 | Shadow between ridges |
| `nap_direction` | vertical | Along the wale |

## GLSL Snippet

```glsl
float corduroy(vec2 uv, float wales) {
    float ridge = sin(uv.x * wales * PI) * 0.5 + 0.5;
    float height = ridge * ridge_height;
    float valley = (1.0 - ridge) * valley_depth;
    return height + valley;
}
```

## Prompt Template

> "Corduroy fabric in [COLOR], [fine/wide] wale vertical ridges with light-channel shadows between, soft compressible pile, classic utility textile"

## Anti-Drift

- **Not velvet**: Corduroy has ridges; velvet is uniform
- **Not rib knit**: Corduroy is woven; rib is knitted
- **Wale width**: The number of ridges per inch defines the type

---

*Weave ridges, cut pile. The wale is the line.*
