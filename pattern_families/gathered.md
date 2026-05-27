# Gathered

Distributed fullness. Elastic or thread.

## What It Is

Gathered fabric has **fullness distributed evenly** along a line, creating soft, regular folds. It's created by pulling thread or elastic to bunch fabric.

## Construction

- **Two rows of stitching**: Running stitch along gather line
- **Pull thread**: Draw up to create folds
- **Even distribution**: Fullness spread uniformly
- **Secure**: Thread knotted to hold gathers

## Visual DNA

- **Soft folds**: Gentle, rounded gathers
- **Even distribution**: Fullness spread along line
- **Volume at edge**: More fabric at gathered edge than flat
- **Temporary or permanent**: Can be basting or final
- **Common uses**: Skirts, curtains, sleeves, ruffles, waistbands

## Shader Parameters

| Parameter | Range | Notes |
|-----------|-------|-------|
| `gather_ratio` | 1.5–3.0 | How much fabric bunched |
| `fold_softness` | 0.3–0.7 | Gentle vs. crisp |
| `distribution` | 0.8–1.0 | Evenness |
| `volume` | 0.0–0.03 | Dimensional fullness |

## GLSL Snippet

```glsl
float gathered(vec2 uv, float ratio) {
    float gather = sin(uv.x * ratio) * gather_amount;
    float fold = smoothstep(0.0, 0.1, gather) * volume;
    return fold;
}
```

## Prompt Template

> "Gathered [GARMENT] in [COLOR], evenly distributed soft folds creating fullness, gentle rounded gathers, classic textile fullness"

## Anti-Drift

- **Not pleated**: Gathered is soft and distributed; pleated is regular and crisp
- **Not ruched**: Gathered is simple fullness; ruched is controlled with elastic
- **Even distribution**: Fullness spread uniformly is key

---

*Pull thread, bunch evenly. The fullness is the gather.*
