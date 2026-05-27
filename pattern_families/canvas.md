# Canvas

Heavy plain weave. Rugged utility.

## What It Is

Canvas is a **heavy, sturdy plain-weave fabric** usually made from cotton, linen, or hemp. It's known for its durability, stiffness, and utility in workwear, sails, and art surfaces.

## Construction

- **Plain weave**: Simple over-under
- **Heavy yarn**: Thick, strong threads
- **Tight weave**: Dense, durable construction
- **Stiff hand**: Holds shape, little drape

## Visual DNA

- **Heavy texture**: Thick, visible threads
- **Stiff drape**: Holds structure, doesn't flow
- **Utility appearance**: Looks tough and practical
- **Visible weave**: Thread structure clearly apparent
- **Common uses**: Tents, sails, workwear, bags, shoes, art canvas, upholstery

## Shader Parameters

| Parameter | Range | Notes |
|-----------|-------|-------|
| `yarn_thickness` | 0.01–0.03 | Heavy visible threads |
| `weave_tightness` | 0.8–1.0 | Dense construction |
| `stiffness` | 0.7–1.0 | Little drape |
| `weight` | heavy | Substantial feel |

## GLSL Snippet

```glsl
float canvas(vec2 uv, float scale) {
    float plain = plain_weave(uv, scale);
    float thick = yarn_texture(uv, yarn_thickness);
    return plain * thick;
}
```

## Prompt Template

> "Canvas fabric in [COLOR], heavy plain-weave cotton with thick visible threads, stiff utility textile, rugged durable construction"

## Anti-Drift

- **Not denim**: Canvas is plain weave; denim is twill
- **Not duck**: Duck is a specific heavy canvas (cotton duck)
- **Utility first**: Designed for durability, not drape

---

*Thick yarn, tight plain weave. The weight is the strength.*
