# Terry Cloth

Looped pile. Absorbent texture.

## What It Is

Terry cloth is a **knitted or woven fabric with uncut loops** on one or both sides. The loops create a highly absorbent, soft surface perfect for towels and bathrobes.

## Construction

- **Loop pile**: Warp or weft threads form loops
- **Uncut**: Loops remain intact (not sheared)
- **High absorbency**: Loops trap water
- **Cotton base**: Usually 100% cotton for absorbency

## Visual DNA

- **Visible loops**: Uncut pile loops clearly visible
- **Soft and plush**: Loops compress when touched
- **Absorbent texture**: Looks like it would soak up water
- **One or two-sided**: Can have loops on one or both sides
- **Common uses**: Towels, bathrobes, beachwear, baby items

## Shader Parameters

| Parameter | Range | Notes |
|-----------|-------|-------|
| `loop_height` | 0.01–0.03 | Uncut loop length |
| `loop_density` | 0.5–1.0 | How packed the loops |
| `side_count` | 1–2 | One-sided or two-sided |
| `compressibility` | 0.3–0.7 | How much loops flatten |

## GLSL Snippet

```glsl
float terry_cloth(vec2 uv, float height) {
    float loops = fbm(uv * 40.0) * height;
    float density = smoothstep(0.3, 0.7, loops);
    return loops * density;
}
```

## Prompt Template

> "Terry cloth towel in [COLOR], uncut loop pile on [one/both] sides, highly absorbent plush texture, visible loop structure, cotton bath textile"

## Anti-Drift

- **Not velour**: Terry has uncut loops; velour has sheared pile
- **Not fleece**: Terry is woven/knitted loops; fleece is brushed knit
- **Absorbency**: The loop structure is for water absorption

---

*Loop, don't cut. The uncut pile is the sponge.*
