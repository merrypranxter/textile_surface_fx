# Denim

Twill weave. Indigo warp.

## What It Is

Denim is a **sturdy cotton twill fabric** with a distinctive diagonal rib, traditionally dyed with indigo on the warp (lengthwise) threads and left white on the weft.

## Construction

- **Twill weave**: Diagonal rib pattern (usually 3/1 twill)
- **Indigo warp**: Lengthwise threads dyed blue
- **White weft**: Crosswise threads undyed
- **Right/wrong side**: Blue face, paler reverse

## Visual DNA

- **Diagonal twill line**: Subtle diagonal texture
- **Indigo blue**: Characteristic blue color (varies by wash)
- **White weft show**: Slight white speckle on surface
- **Sturdy and stiff**: Heavy, durable appearance
- **Common uses**: Jeans, jackets, workwear, casual fashion, accessories

## Shader Parameters

| Parameter | Range | Notes |
|-----------|-------|-------|
| `twill_angle` | 30°–60° | Diagonal direction |
| `indigo_depth` | 0.5–1.0 | How dark the blue |
| `white_speckle` | 0.0–0.2 | Weft visibility |
| `stiffness` | 0.5–0.9 | Heavy drape |

## GLSL Snippet

```glsl
float denim(vec2 uv, float angle) {
    float twill = twill_weave(uv, angle, scale);
    float indigo = indigo_dye(uv, depth);
    float speckle = white_weft(uv, scale) * speckle_amount;
    return twill * indigo + speckle;
}
```

## Prompt Template

> "Denim fabric in [indigo/dark/mid/light] wash, cotton twill with diagonal rib, indigo warp white weft structure, sturdy workwear textile"

## Anti-Drift

- **Not chambray**: Denim is twill; chambray is plain weave
- **Not canvas**: Denim is twill; canvas is plain weave
- **Indigo specifically**: Traditional dye is indigo

---

*Twill, indigo, white weft. The diagonal is the jean.*
