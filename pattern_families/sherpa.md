# Sherpa

Deep pile. Faux shearling.

## What It Is

Sherpa is a **heavy, deep-pile fabric** that mimics sheepskin or shearling. It has a dense, fluffy surface that resembles wool fleece, often used as lining or cozy outerwear.

## Construction

- **Knitted or woven base**: Heavy fabric construction
- **Deep pile**: Very long, fluffy fibers
- **Two-tone**: Often darker at base, lighter at tips
- **Synthetic or wool**: Can be acrylic, polyester, or wool

## Visual DNA

- **Deep fluffy pile**: Very thick, plush surface
- **Sheepskin illusion**: Resembles natural shearling
- **Two-tone texture**: Dark roots, light tips
- **Very warm**: Looks insulating and cozy
- **Common uses**: Coats, jackets, blankets, slippers, linings, winter wear

## Shader Parameters

| Parameter | Range | Notes |
|-----------|-------|-------|
| `pile_depth` | 0.02–0.08 | Very deep pile |
| `fluff_density` | 0.8–1.0 | How packed |
| `two_tone` | 0.0–0.5 | Dark base, light tips |
| `warmth_appearance` | 0.9–1.0 | Looks very insulating |

## GLSL Snippet

```glsl
float sherpa(vec2 uv, float depth) {
    float pile = fbm(uv * 20.0 + depth * 50.0) * depth;
    float base = mix(dark_color, light_color, pile / depth);
    return base;
}
```

## Prompt Template

> "Sherpa fabric in [COLOR], deep fluffy pile mimicking sheepskin shearling, two-tone dark roots light tips, extremely warm cozy textile"

## Anti-Drift

- **Not fleece**: Sherpa is deeper pile than fleece
- **Not shearling**: Sherpa is faux; shearling is real sheepskin
- **Synthetic wool-look**: Mimics natural wool appearance

---

*Deep pile, two-tone, fluffy. The sheep is the illusion.*
