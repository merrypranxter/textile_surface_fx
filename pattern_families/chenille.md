# Chenille

Cut pile. Fuzzy caterpillar.

## What It Is

Chenille is a **fabric with a fuzzy, caterpillar-like pile** created by wrapping short lengths of yarn around a core yarn, then weaving or tufting. The result is soft, plush, and slightly iridescent.

## Construction

- **Chenille yarn**: Short pile fibers twisted around core
- **Weaving or tufting**: Applied to base fabric
- **Cut pile**: Pile is cut, not looped
- **Directional sheen**: Light catches pile differently by angle

## Visual DNA

- **Fuzzy caterpillar**: Pile resembles a fuzzy worm
- **Soft and plush**: Very tactile, comfortable
- **Slight iridescence**: Light reflects off angled fibers
- **Directional**: Pile has a nap direction
- **Common uses**: Robes, bedding, upholstery, baby items, vintage clothing

## Shader Parameters

| Parameter | Range | Notes |
|-----------|-------|-------|
| `pile_height` | 0.01–0.05 | Fiber length |
| `fuzzy_factor` | 0.5–1.0 | How fuzzy the surface |
| `iridescence` | 0.0–0.3 | Light-angle color shift |
| `nap_direction` | 0°–360° | Pile angle |

## GLSL Snippet

```glsl
float chenille(vec2 uv, float height, float seed) {
    float pile = fbm(uv * 50.0 + seed) * height;
    float sheen = pow(dot(view, nap), 2.0) * iridescence;
    return pile + sheen;
}
```

## Prompt Template

> "Chenille fabric in [COLOR], fuzzy caterpillar-like pile with soft plush texture, slight directional iridescence, comfortable tactile textile"

## Anti-Drift

- **Not velvet**: Chenille has twisted pile; velvet has sheared uniform pile
- **Not fleece**: Chenille is woven; fleece is knitted
- **Caterpillar texture**: The fuzzy worm-like appearance is signature

---

*Twist, wrap, cut. The caterpillar is the pile.*
