# Fleece

Brushed knit. Synthetic warmth.

## What It Is

Fleece is a **brushed synthetic knit fabric** with a soft, fuzzy pile on one or both sides. It mimics wool's warmth but is lightweight, quick-drying, and machine washable.

## Construction

- **Knitted base**: Polyester knit fabric
- **Brushed pile**: Mechanical brushing raises fibers
- **Anti-pill treatment**: Prevents fiber balls from forming
- **Lightweight**: Warm without weight

## Visual DNA

- **Soft fuzz**: Fine, uniform fuzzy surface
- **Matte appearance**: No shine, very soft look
- **Light and airy**: Looks warm but not heavy
- **Pill potential**: Slight fiber balls on surface (unless anti-pill)
- **Common uses**: Jackets, blankets, sportswear, outdoor gear, linings

## Shader Parameters

| Parameter | Range | Notes |
|-----------|-------|-------|
| `fuzz_length` | 0.005–0.015 | Brushed fiber height |
| `pile_uniformity` | 0.7–1.0 | Even fuzz distribution |
| `pill_amount` | 0.0–0.3 | Fiber ball visibility |
| `weight` | light | Appears lightweight |

## GLSL Snippet

```glsl
float fleece(vec2 uv, float fuzz) {
    float base = knit_texture(uv, scale);
    float pile = fbm(uv * 60.0) * fuzz;
    float pills = cellular_noise(uv * 20.0) * pill_amount;
    return base + pile + pills;
}
```

## Prompt Template

> "Fleece fabric in [COLOR], soft brushed synthetic knit with uniform fuzzy pile, lightweight warmth, matte appearance, outdoor sportswear textile"

## Anti-Drift

- **Not wool**: Fleece is synthetic polyester; wool is natural
- **Not sherpa**: Fleece is smooth fuzz; sherpa is deep pile
- **Brushed knit**: The fuzz comes from mechanical brushing

---

*Knit, brush, raise. The fuzz is the warmth.*
