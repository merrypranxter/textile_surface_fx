# Tweed

Slubbed yarn. Earthy texture.

## What It Is

Tweed is a **rough, woolen fabric** with a distinctive slubbed texture created by using yarns of different colors and thicknesses. It's associated with rural Scotland and traditional British tailoring.

## Construction

- **Woolen yarn**: Spun wool, often multi-colored
- **Slubbed texture**: Thick and thin sections in yarn
- **Plain or twill weave**: Simple weave structures
- **Melange effect**: Mixed colors create heathered appearance

## Visual DNA

- **Rough texture**: Slightly coarse, nubby surface
- **Heathered color**: Mixed fiber colors create depth
- **Slubbed irregularity**: Thick and thin yarns visible
- **Earthy tones**: Traditional browns, greens, greys
- **Common uses**: Suits, jackets, coats, caps, traditional British wear

## Shader Parameters

| Parameter | Range | Notes |
|-----------|-------|-------|
| `slub_size` | 0.01–0.05 | Thick yarn sections |
| `color_melange` | 0.3–0.7 | Mixed fiber visibility |
| `roughness` | 0.3–0.6 | Surface texture |
| `earthiness` | 0.6–1.0 | Natural tone dominance |

## GLSL Snippet

```glsl
float tweed(vec2 uv, float seed) {
    float slubs = fbm(uv * 15.0 + seed) * slub_size;
    float melange = noise(uv * 10.0 + seed * 2.0) * color_melange;
    float weave = twill_pattern(uv, scale);
    return weave + slubs + melange;
}
```

## Prompt Template

> "Tweed fabric in [COLOR] heathered wool, rough slubbed texture with thick-thin yarn variation, earthy melange color, traditional British textile"

## Anti-Drift

- **Not bouclé**: Tweed has slubs; bouclé has loops
- **Not herringbone**: Herringbone is a weave pattern; tweed is a fabric type
- **Woolen**: Tweed is wool; similar textures in other fibers are tweed-look

---

*Thick, thin, mix, weave. The slub is the countryside.*
