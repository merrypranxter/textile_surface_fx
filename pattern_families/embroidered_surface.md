# Embroidered Surface

Stitched texture. Thread as relief.

## What It Is

Embroidered surface refers to **any fabric with surface embroidery** creating textured, raised, or decorative patterns. The stitching itself becomes the surface texture.

## Construction

- **Various stitches**: Any embroidery stitch type
- **Surface application**: Worked on top of base fabric
- **Dimensional**: Stitches sit proud of fabric
- **Thread variety**: Different weights and types for texture

## Visual DNA

- **Visible stitches**: Thread patterns on fabric surface
- **Textural variety**: Smooth satin, bumpy French knots, twisted stem
- **Color and thread**: Different threads create visual interest
- **Dimensional relief**: Raised areas from padding or dense stitching
- **Common uses**: Decorative fabrics, couture, folk costumes, home textiles

## Shader Parameters

| Parameter | Range | Notes |
|-----------|-------|-------|
| `stitch_type` | varied | Satin, stem, knot, etc. |
| `relief` | 0.0–0.02 | Dimensional height |
| `thread_weight` | 0.001–0.01 | Thickness |
| `coverage` | 0.2–1.0 | How much surface covered |

## GLSL Snippet

```glsl
float embroidered_surface(vec2 uv, float relief) {
    float stitches = embroidery_pattern(uv, scale);
    float height = stitches * relief;
    float thread = thread_texture(uv, thickness);
    return height + thread;
}
```

## Prompt Template

> "Embroidered surface in [COLOR] thread on [FABRIC], [STITCH TYPE] creating textured relief, dimensional stitched pattern, decorative textile art"

## Anti-Drift

- **Not woven pattern**: Embroidery is added; woven is integral
- **Not printed**: Embroidery is physical thread; print is flat color
- **Surface only**: Stitches sit on top of base fabric

---

*Stitch on top. The thread is the surface.*
