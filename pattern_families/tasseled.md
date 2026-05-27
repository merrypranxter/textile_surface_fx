# Tasseled

Hanging cluster. Ornamental weight.

## What It Is

Tassels are **decorative hanging clusters of threads** attached to fabric edges, cords, or corners. They add weight, movement, and ornamentation to textiles.

## Construction

- **Thread bundle**: Many threads gathered together
- **Head binding**: Threads tied near top to form head
- **Skirt**: Loose threads hanging below head
- **Attachment**: Sewn or tied to fabric

## Visual DNA

- **Cluster shape**: Bulbous head with hanging skirt
- **Movement**: Swings with motion
- **Ornamental**: Decorative rather than functional
- **Weight**: Adds physical heaviness to corner or edge
- **Common uses**: Cushions, curtains, academic dress, ethnic costume, bags, furniture

## Shader Parameters

| Parameter | Range | Notes |
|-----------|-------|-------|
| `tassel_size` | 0.02–0.1 | Overall dimensions |
| `skirt_length` | 0.02–0.08 | Hanging thread length |
| `head_size` | 0.005–0.02 | Bulbous top |
| `thread_count` | 10–100 | Number of threads |

## GLSL Snippet

```glsl
float tassel(vec2 uv, float size) {
    float head = smoothstep(size, size - 0.01, length(uv));
    float skirt = smoothstep(0.0, skirt_length, uv.y) * (1.0 - head);
    float threads = fbm(uv * 30.0) * 0.1;
    return head + skirt + threads;
}
```

## Prompt Template

> "Tasseled [ITEM] in [COLOR], hanging thread cluster with bulbous head and flowing skirt, ornamental weight and movement, decorative textile accent"

## Anti-Drift

- **Not fringe**: Tassel is hanging cluster; fringe is edge threads
- **Not pom-pom**: Tassel has hanging skirt; pom-pom is spherical
- **Weight function**: Often adds weight to hold fabric in place

---

*Gather, tie, let hang. The cluster is the ornament.*
