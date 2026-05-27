# Quilted Surface

Stitched sandwich. Padded texture.

## What It Is

Quilted surface is **three layers (top, batting, backing) held together by stitching**, creating a padded, textured surface with visible stitch lines and slight dimensional relief.

## Construction

- **Three layers**: Top fabric, batting, backing
- **Quilting stitches**: Hold layers together
- **Pattern or utilitarian**: Can be decorative or simple
- **Machine or hand**: Various quilting methods

## Visual DNA

- **Stitch lines**: Visible quilting pattern
- **Slight puff**: Batting creates subtle dimension
- **Shadow texture**: Stitches catch light
- **Patterned or grid**: Can be elaborate or simple
- **Common uses**: Jackets, bags, bedspreads, luxury items

## Shader Parameters

| Parameter | Range | Notes |
|-----------|-------|-------|
| `stitch_pattern` | grid/freeform | Quilting design |
| `puff_amount` | 0.0–0.02 | Batting thickness |
| `stitch_density` | 0.2–1.0 | How much stitched |
| `shadow_depth` | 0.0–0.01 | Light catch |

## GLSL Snippet

```glsl
float quilted_surface(vec2 uv, float density) {
    float stitches = quilting_pattern(uv, scale);
    float puff = (1.0 - stitches) * batting_thickness;
    float shadow = stitches * stitch_depth;
    return puff + shadow;
}
```

## Prompt Template

> "Quilted surface in [COLOR] with [PATTERN] stitching, padded three-layer texture with visible stitch lines, subtle dimensional puff, luxury textile"

## Anti-Drift

- **Not padded fabric**: Quilted has visible stitches; padded may not
- **Three layers essential**: Top, batting, backing
- **Not trapunto**: Quilted is flat padding; trapunto is stuffed areas

---

*Sandwich, stitch, puff. The stitch is the structure.*
