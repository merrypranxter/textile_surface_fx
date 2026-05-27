# Velvet

Sheared pile. Light and shadow.

## What It Is

Velvet is a **woven fabric with a dense, soft pile** created by weaving two layers simultaneously and cutting the connecting threads. The sheared pile catches light dramatically.

## Construction

- **Double cloth weaving**: Two layers woven together
- **Pile warp**: Extra warp threads form loops
- **Shearing**: Loops cut to create uniform pile
- **Nap direction**: Pile lies in one direction

## Visual DNA

- **Lustrous pile**: Light catches and reflects from pile
- **Light/dark shift**: Color changes with viewing angle ("shading")
- **Soft hand**: Luxurious, tactile surface
- **Crushed variant**: Pressed pile creates random pattern
- **Common uses**: Evening wear, upholstery, curtains, luxury fashion

## Shader Parameters

| Parameter | Range | Notes |
|-----------|-------|-------|
| `pile_height` | 0.005–0.02 | Sheared fiber length |
| `sheen_intensity` | 0.3–0.8 | Light reflection |
| `nap_angle` | 0°–360° | Pile direction |
| `crush_factor` | 0.0–0.5 | For crushed velvet |

## GLSL Snippet

```glsl
float velvet(vec2 uv, float height, float nap) {
    float pile = smoothstep(0.0, height, fbm(uv * 30.0));
    float sheen = pow(max(0.0, dot(view, nap)), 3.0);
    float crush = crush_pattern(uv, crush_factor);
    return pile * sheen + crush;
}
```

## Prompt Template

> "Velvet fabric in [COLOR], dense sheared pile with dramatic light-catch shading, luxurious nap texture, [plain/crushed] velvet textile"

## Anti-Drift

- **Not chenille**: Velvet has uniform sheared pile; chenille has twisted fuzzy pile
- **Not corduroy**: Velvet is uniform; corduroy has ridges
- **Nap matters**: Direction of pile changes appearance

---

*Weave double, cut, shear. The pile is the light.*
