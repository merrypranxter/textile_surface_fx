# Linen Texture

Slubbed crispness. Natural irregularity.

## What It Is

Linen fabric has a **characteristic crisp texture** with natural slubs (thick and thin areas) in the yarn, giving it a distinctive, slightly irregular, elegant appearance.

## Construction

- **Flax fibers**: Spun from flax plant stems
- **Slubbed yarn**: Natural thick-thin variation
- **Crisp hand**: Stiffens when ironed, softens with wash
- **Cool touch**: Feels cool against skin

## Visual DNA

- **Visible slubs**: Thick-thin irregularities in yarn
- **Crisp texture**: Structured, holds shape
- **Natural luster**: Subtle sheen from flax fiber
- **Wrinkle-prone**: Creases easily (sign of real linen)
- **Common uses**: Summer suits, shirts, tablecloths, napkins, bedding

## Shader Parameters

| Parameter | Range | Notes |
|-----------|-------|-------|
| `slub_density` | 0.3–0.7 | Thick-thin variation |
| `crispness` | 0.6–0.9 | Structured drape |
| `natural_luster` | 0.2–0.5 | Subtle sheen |
| `wrinkle_amount` | 0.0–0.3 | Crease texture |

## GLSL Snippet

```glsl
float linen(vec2 uv, float seed) {
    float slubs = fbm(uv * 20.0 + seed) * slub_density;
    float weave = plain_weave(uv, scale);
    float crisp = crispness * weave;
    return slubs + crisp;
}
```

## Prompt Template

> "Linen fabric in [COLOR], natural flax texture with visible slubs and crisp hand, subtle luster, elegant summer textile"

## Anti-Drift

- **Not cotton**: Linen is flax; cotton is different fiber
- **Slubs are natural**: Thick-thin is inherent to flax yarn
- **Crispness**: Linen is naturally stiffer than cotton

---

*Flax, slub, crisp. The irregularity is the elegance.*
