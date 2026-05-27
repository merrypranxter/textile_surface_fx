# Fringed

Loose threads. Unraveled edge.

## What It Is

Fringed fabric has **loose thread ends extending from the edge**, created by unraveling warp or weft threads and securing the remaining threads. It's decorative and can be functional.

## Construction

- **Unravel edge**: Threads removed from fabric edge
- **Secure remaining**: Base threads tied or secured
- **Even length**: Fringe cut to uniform length
- **Various styles**: Brush, knotted, twisted, bullion

## Visual DNA

- **Loose threads**: Individual strands hanging from edge
- **Even or uneven**: Can be uniform or varied
- **Textured edge**: Soft, fuzzy boundary
- **Movement**: Threads sway with motion
- **Common uses**: Scarves, shawls, rugs, curtains, Western wear, ethnic dress

## Shader Parameters

| Parameter | Range | Notes |
|-----------|-------|-------|
| `fringe_length` | 0.02–0.1 | Thread hang length |
| `thread_density` | 0.5–1.0 | How packed the threads |
| `evenness` | 0.3–1.0 | Uniform vs. varied |
| `style` | brush/knotted/twisted | Fringe type |

## GLSL Snippet

```glsl
float fringed(vec2 uv, float length) {
    float threads = fbm(uv * 50.0) * length;
    float density = smoothstep(0.0, 0.1, threads);
    float sway = sin(uv.x * 10.0 + time) * 0.01;
    return threads + sway;
}
```

## Prompt Template

> "Fringed [ITEM] in [COLOR], loose thread ends extending from edge, [brush/knotted/twisted] fringe style, soft textured boundary textile"

## Anti-Drift

- **Not hemmed**: Fringe is loose threads; hem is folded edge
- **Not tasseled**: Fringe is along edge; tassel is hanging cluster
- **Unraveled**: Created by removing threads from woven edge

---

*Unravel, secure, cut even. The loose thread is the edge.*
