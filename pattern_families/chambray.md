# Chambray

Plain weave, dyed warp, white weft. Denim's lighter cousin.

## What It Is

Chambray is a **plain-weave cotton fabric** with a colored (usually blue) warp and white weft, creating a soft, even, slightly lustrous surface. It looks like denim but is lighter and softer.

## Construction

- **Plain weave**: Over-under basic weave (not twill)
- **Colored warp**: Lengthwise threads dyed
- **White weft**: Crosswise threads undyed
- **Even surface**: No diagonal rib like denim

## Visual DNA

- **Soft blue**: Lighter, softer than denim
- **Even texture**: Plain weave creates flat surface
- **Slight sheen**: Warp-dyed surface has subtle luster
- **Casual elegance**: Looks refined but relaxed
- **Common uses**: Shirts, dresses, casual wear, work shirts, summer clothing

## Shader Parameters

| Parameter | Range | Notes |
|-----------|-------|-------|
| `warp_color` | blue/other | Usually blue |
| `weft_white` | 0.5–1.0 | How visible white |
| `weave_evenness` | 0.8–1.0 | Plain weave regularity |
| `softness` | 0.6–0.9 | Light drape |

## GLSL Snippet

```glsl
float chambray(vec2 uv, float scale) {
    float plain = plain_weave(uv, scale);
    float warp = warp_color * plain;
    float weft = weft_white * (1.0 - plain);
    return warp + weft;
}
```

## Prompt Template

> "Chambray fabric in [COLOR], plain-weave cotton with colored warp and white weft, soft even surface, lighter cousin of denim, casual shirt textile"

## Anti-Drift

- **Not denim**: Chambray is plain weave; denim is twill
- **Not oxford**: Chambray is single yarn; oxford is basket weave
- **Lighter than denim**: Softer hand, less stiff

---

*Plain weave, blue warp, white weft. The evenness is the softness.*
