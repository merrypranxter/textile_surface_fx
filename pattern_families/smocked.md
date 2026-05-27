# Smocked

Stitched gathers. Honeycomb texture.

## What It Is

Smocked fabric has **decorative stitching over gathered fabric**, creating a textured, honeycomb-like pattern with elastic properties. It's traditional in children's clothing and folk dress.

## Construction

- **Gathered base**: Fabric gathered with multiple rows
- **Decorative stitches**: Overcast or cable stitches hold gathers
- **Elastic effect**: Stitches allow stretch and recovery
- **Geometric patterns**: Honeycomb, wave, diamond designs

## Visual DNA

- **Honeycomb texture**: Diamond or hexagonal stitched patterns
- **Gathered base**: Fabric bunched underneath stitches
- **Elastic stretch**: Can expand and contract
- **Traditional look**: Associated with children's and folk clothing
- **Common uses**: Children's dresses, bishop sleeves, folk costumes, blouses

## Shader Parameters

| Parameter | Range | Notes |
|-----------|-------|-------|
| `smock_pattern` | honeycomb/wave/diamond | Stitch design |
| `gather_density` | 0.3–0.8 | How bunched the base |
| `stitch_visibility` | 0.3–0.7 | How visible decorative stitches |
| `elasticity` | 0.3–0.7 | Stretch amount |

## GLSL Snippet

```glsl
float smocked(vec2 uv, float density) {
    float gather = sin(uv.x * density) * gather_amount;
    float honeycomb = diamond_stitch(uv, scale) * stitch_visibility;
    return gather + honeycomb;
}
```

## Prompt Template

> "Smocked [GARMENT] in [COLOR], honeycomb/wave/diamond decorative stitches over gathered fabric, elastic textured surface, traditional children's textile"

## Anti-Drift

- **Not ruched**: Smocked has decorative stitches; ruched is just gathered
- **Not shirred**: Shirring is elastic thread rows; smocking is decorative hand stitches
- **Hand stitched**: Traditional smocking is handwork

---

*Gather, stitch decoratively. The honeycomb is the handwork.*
