# Ruched

Elastic gather. Controlled scrunch.

## What It Is

Ruched fabric is **gathered or pleated with elastic or thread**, creating soft, controlled folds that add texture and volume. It's more organic than pleating but more controlled than gathering.

## Construction

- **Elastic or thread**: Gathering mechanism
- **Controlled placement**: Folds where designer wants them
- **Soft folds**: Less crisp than pleats
- **Stretch and release**: Elastic allows movement

## Visual DNA

- **Soft folds**: Gentle, rounded gathers
- **Elastic texture**: Slight stretch visible
- **Volume and texture**: Adds dimension to fabric
- **Controlled chaos**: Organized but organic
- **Common uses**: Dresses, tops, swimwear, lingerie, decorative elements

## Shader Parameters

| Parameter | Range | Notes |
|-----------|-------|-------|
| `fold_softness` | 0.3–0.7 | Rounded vs. crisp |
| `elastic_tension` | 0.2–0.8 | How tight the gather |
| `volume` | 0.0–0.05 | Dimensional puff |
| `irregularity` | 0.1–0.5 | Organic variation |

## GLSL Snippet

```glsl
float ruched(vec2 uv, float tension) {
    float gather = sin(uv.x * frequency) * (1.0 - tension) * 0.5;
    float fold = smoothstep(0.0, 0.1, gather) * volume;
    return fold;
}
```

## Prompt Template

> "Ruched [GARMENT] in [COLOR], soft elastic-controlled gathers with gentle rounded folds, added volume and texture, decorative textile detail"

## Anti-Drift

- **Not pleated**: Ruched is soft and elastic; pleated is crisp and permanent
- **Not gathered**: Ruched is controlled placement; gathering is distributed
- **Elastic-based**: Stretch mechanism is part of definition

---

*Pull elastic, release. The scrunch is the volume.*
