# Sequin

Reflective discs. Sparkle surface.

## What It Is

Sequin fabric has **small reflective discs sewn or glued** onto the surface, creating a glittering, light-catching effect. Sequins can be flat, cupped, holographic, or shaped.

## Construction

- **Sequin discs**: Plastic or metal discs with hole for attachment
- **Sewn or glued**: Attached to fabric surface
- **Overlapping or scattered**: Can be dense or sparse
- **Various shapes**: Round, square, star, paillette

## Visual DNA

- **Sparkle and shine**: Light reflects off discs
- **Dimensional**: Discs sit proud of fabric
- **Movement glitter**: Sparkle changes with motion
- **Dense or scattered**: Full coverage or accent placement
- **Common uses**: Evening wear, costumes, dancewear, accessories, festive

## Shader Parameters

| Parameter | Range | Notes |
|-----------|-------|-------|
| `sequin_size` | 0.005–0.02 | Disc diameter |
| `coverage` | 0.1–1.0 | How dense the sequins |
| `reflectivity` | 0.5–1.0 | Light catch |
| `dimensionality` | 0.0–0.01 | Disc height off fabric |

## GLSL Snippet

```glsl
float sequin(vec2 uv, float size) {
    vec2 cell = floor(uv / size);
    vec2 local = fract(uv / size) - 0.5;
    float disc = smoothstep(0.0, 0.1, length(local) - size * 0.5);
    float shine = pow(dot(normal, light), 4.0) * reflectivity;
    return disc * shine;
}
```

## Prompt Template

> "Sequin fabric in [COLOR] with [SHAPE] sequins, reflective light-catching discs [overlapping/scattered] on fabric surface, sparkle evening wear textile"

## Anti-Drift

- **Not glitter**: Sequins are discrete discs; glitter is fine particles
- **Not beads**: Sequins are flat discs; beads are 3D objects
- **Reflective**: The light catch is the purpose

---

*Disc, sew, shine. The sparkle is the surface.*
