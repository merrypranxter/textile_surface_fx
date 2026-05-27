# Bouclé

Looped yarn. Curly texture.

## What It Is

Bouclé is a **fabric made from looped yarns** that create a textured, curly, nubby surface. The loops are part of the yarn structure, not brushed or sheared afterward.

## Construction

- **Looped yarn**: Yarn has intentional loops and curls
- **Woven or knitted**: Looped yarn used as weft or filling
- **Nubby texture**: Small bumps and curls on surface
- **Tight weave**: Loops held in place by construction

## Visual DNA

- **Curly loops**: Small curls and loops visible
- **Nubby texture**: Bumpy, irregular surface
- **Tactile interest**: Looks like it would feel interesting
- **Slight dimension**: Loops sit proud of base fabric
- **Common uses**: Jackets, coats, upholstery, accessories, Chanel-style suits

## Shader Parameters

| Parameter | Range | Notes |
|-----------|-------|-------|
| `loop_size` | 0.005–0.02 | Yarn loop dimensions |
| `nub_density` | 0.5–1.0 | How bumpy the surface |
| `yarn_thickness` | 0.003–0.01 | Bouclé yarn diameter |
| `tightness` | 0.7–1.0 | How secure loops are |

## GLSL Snippet

```glsl
float boucle(vec2 uv, float size) {
    float loops = fbm(uv * 30.0) * size;
    float nubs = cellular_noise(uv * 25.0) * nub_density;
    return loops + nubs;
}
```

## Prompt Template

> "Bouclé fabric in [COLOR], looped yarn creating curly nubby texture, tactile bumpy surface, Chanel-style jacket textile"

## Anti-Drift

- **Not chenille**: Bouclé loops are in yarn; chenille pile is cut
- **Not tweed**: Bouclé has loops; tweed has slubs
- **Yarn structure**: The loop is part of the yarn, not added later

---

*Loop the yarn, weave the loop. The curl is the texture.*
