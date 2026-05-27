# Silk Texture

Smooth luster. Natural protein fiber.

## What It Is

Silk fabric has a **smooth, lustrous surface** with a soft, flowing drape. The natural protein fiber creates a distinctive sheen and temperature-regulating quality.

## Construction

- **Silk filaments**: Spun from silkworm cocoons
- **Smooth yarn**: Very fine, even threads
- **Various weaves**: Plain, twill, satin, crepe
- **Natural luster**: Fiber structure creates shine

## Visual DNA

- **High luster**: Reflective, shiny surface
- **Smooth hand**: Very soft, slippery feel
- **Flowing drape**: Elegant, fluid movement
- **Temperature regulating**: Cool in summer, warm in winter
- **Common uses**: Evening wear, scarves, ties, bedding, luxury fashion

## Shader Parameters

| Parameter | Range | Notes |
|-----------|-------|-------|
| `luster` | 0.5–0.9 | Light reflection |
| `smoothness` | 0.8–1.0 | Surface evenness |
| `drape` | fluid | Flowing movement |
| `sheen_color` | — | Slight color shift in light |

## GLSL Snippet

```glsl
float silk(vec2 uv, float shine) {
    float base = weave_texture(uv, scale);
    float sheen = pow(dot(normal, light), 2.0) * shine;
    float drape = fabric_fold(uv, drape_factor);
    return base + sheen + drape * 0.1;
}
```

## Prompt Template

> "Silk fabric in [COLOR], smooth lustrous surface with flowing drape, natural protein fiber sheen, luxury evening wear textile"

## Anti-Drift

- **Not satin**: Silk is a fiber; satin is a weave (silk can be satin)
- **Not polyester**: Real silk is protein; synthetic is different
- **Natural luster**: The shine comes from fiber structure, not coating

---

*Filament, smooth, shine. The cocoon is the luxury.*
