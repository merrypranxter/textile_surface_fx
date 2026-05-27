# Satin Texture

Float weave. Maximum shine.

## What It Is

Satin is a **weave structure** (not a fiber) where warp threads "float" over multiple weft threads, creating a smooth, highly reflective surface with minimal visible weave pattern.

## Construction

- **Float weave**: Warp passes over 4+ weft threads
- **Minimal intersections**: Very few thread crossing points
- **Smooth face**: Long floats create glossy surface
- **Dull reverse**: Back side is matte

## Visual DNA

- **Maximum shine**: Highest light reflection of any weave
- **Smooth surface**: Almost no visible weave texture
- **Glossy face**: Front is shiny; back is dull
- **Sleek drape**: Fluid, slippery movement
- **Common uses**: Evening wear, lingerie, linings, luxury bedding, ribbons

## Shader Parameters

| Parameter | Range | Notes |
|-----------|-------|-------|
| `float_length` | 4–8 | Warp threads per float |
| `shine_intensity` | 0.7–1.0 | Maximum reflectivity |
| `weave_visibility` | 0.0–0.1 | Almost invisible |
| `drape_slipperiness` | 0.8–1.0 | Sleek movement |

## GLSL Snippet

```glsl
float satin(vec2 uv, float floats) {
    float weave = float_weave(uv, floats, scale);
    float shine = pow(max(0.0, dot(normal, half_vector)), 16.0);
    float back = 1.0 - shine; // Dull reverse
    return shine * front + back * 0.1;
}
```

## Prompt Template

> "Satin weave in [COLOR/FIBER], maximum shine from long warp floats, smooth glossy surface with sleek drape, luxury evening wear textile"

## Anti-Drift

- **Not silk**: Satin is a weave; silk is a fiber (silk can be satin)
- **Not sateen**: Satin is warp-faced; sateen is weft-faced
- **Weave structure**: The float is what creates the shine

---

*Float over many, intersect rarely. The shine is the weave.*
