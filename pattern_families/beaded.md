# Beaded Surface

Dimensional embellishment. Tactile luxury.

## What It Is

Beaded fabric has **small beads sewn onto the surface** in patterns or scattered, creating dimensional texture, sparkle, and weight. Beads can be seed beads, bugle beads, crystals, or pearls.

## Construction

- **Bead types**: Seed, bugle, crystal, pearl, sequin-bead mix
- **Sewn attachment**: Beads stitched to fabric with needle and thread
- **Patterns or scatter**: Can form images or be random
- **Dimensional weight**: Beads add physical weight to fabric

## Visual DNA

- **Dimensional beads**: Small spheres or tubes sitting on surface
- **Sparkle or matte**: Depending on bead type
- **Tactile texture**: You can feel each bead
- **Patterned or random**: Ordered designs or scattered accent
- **Common uses**: Evening wear, bridal, accessories, couture, ethnic dress

## Shader Parameters

| Parameter | Range | Notes |
|-----------|-------|-------|
| `bead_size` | 0.002–0.01 | Diameter |
| `coverage` | 0.1–1.0 | How dense |
| `bead_type` | seed/bugle/crystal | Shape and material |
| `pattern` | scattered/ordered | Arrangement |

## GLSL Snippet

```glsl
float beaded(vec2 uv, float size) {
    vec2 cell = floor(uv / spacing);
    float bead = smoothstep(size, size - 0.001, length(fract(uv / spacing) - 0.5));
    float shine = pow(dot(normal, light), 3.0) * reflectivity;
    return bead * shine;
}
```

## Prompt Template

> "Beaded [PATTERN] in [COLOR] beads on [FABRIC], dimensional seed/bugle/crystal beads sewn in [pattern], tactile sparkle embellishment, couture textile"

## Anti-Drift

- **Not sequin**: Beads are 3D spheres/tubes; sequins are flat discs
- **Not embroidery**: Beads are separate objects; embroidery is thread
- **Weight**: Beads add physical heaviness to fabric

---

*Stitch each bead, one by one. The dimension is the labor.*
