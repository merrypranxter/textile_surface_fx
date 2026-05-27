# Pleated

Folded precision. Accordion geometry.

## What It Is

Pleated fabric has **regular, permanent folds** pressed or sewn into the material, creating a structured, accordion-like surface that adds texture and expands/contracts with movement.

## Construction

- **Regular folds**: Even, measured folds
- **Heat/steam set**: Permanent pleating (synthetic fabrics)
- **Stitched or pressed**: Various pleating methods
- **Various widths**: Knife, box, accordion, sunburst pleats

## Visual DNA

- **Regular ridges**: Even, parallel folds
- **Shadow valleys**: Deep shadows between pleats
- **Structured and crisp**: Architectural precision
- **Movement expansion**: Fabric spreads when pulled
- **Common uses**: Skirts, dresses, lampshades, fans, kilts, accordion curtains

## Shader Parameters

| Parameter | Range | Notes |
|-----------|-------|-------|
| `pleat_width` | 0.01–0.05 | Fold spacing |
| `pleat_depth` | 0.0–0.03 | Fold height |
| `pleat_type` | knife/box/accordion | Fold style |
| `crispness` | 0.5–1.0 | How sharp the fold |

## GLSL Snippet

```glsl
float pleated(vec2 uv, float width) {
    float fold = sin(uv.x * PI / width);
    float height = fold * pleat_depth;
    float shadow = smoothstep(0.0, 1.0, fold) * shadow_amount;
    return height + shadow;
}
```

## Prompt Template

> "Pleated [GARMENT] in [COLOR], [knife/box/accordion] pleats with regular ridges and shadow valleys, structured crisp fold texture, architectural textile"

## Anti-Drift

- **Not gathered**: Pleats are regular and even; gathers are irregular
- **Not ruched**: Pleats are pressed folds; ruching is elastic gathering
- **Permanent**: True pleats are set, not temporary folds

---

*Fold, press, repeat. The ridge is the geometry.*
