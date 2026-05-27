# Ruffled

Decorative gather. Frilly edge.

## What It Is

A ruffle is a **strip of fabric gathered along one edge** and attached to another fabric, creating a decorative frill or flounce. It adds volume, movement, and ornamentation.

## Construction

- **Strip cut**: Fabric cut in long strip
- **One edge gathered**: Running stitch drawn up
- **Attached**: Sewn to base fabric along gathered edge
- **Flounce**: Free edge hangs or flares

## Visual DNA

- **Decorative frill**: Wavy, flouncy edge
- **Volume at attachment**: Bunched where sewn
- **Flared free edge**: Spreads where not attached
- **Feminine and decorative**: Ornamental rather than functional
- **Common uses**: Children's clothing, lingerie, curtains, pillows, dresses

## Shader Parameters

| Parameter | Range | Notes |
|-----------|-------|-------|
| `ruffle_depth` | 0.01–0.05 | How far it extends |
| `gather_tightness` | 0.3–0.8 | How bunched at attachment |
| `flounce_amount` | 0.5–1.5 | How much flare at free edge |
| `layer_count` | 1–5 | Single or multiple tiers |

## GLSL Snippet

```glsl
float ruffled(vec2 uv, float depth) {
    float gather = sin(uv.x * gather_freq) * gather_amount;
    float flounce = (1.0 - uv.y / depth) * flounce_amount;
    float ruffle = gather * flounce;
    return ruffle;
}
```

## Prompt Template

> "Ruffled [GARMENT] in [COLOR], gathered strip creating decorative frill with flouncy free edge, [single/tiered] ruffle, feminine ornamental textile"

## Anti-Drift

- **Not gathered**: Ruffle is a gathered strip applied; gathering is technique
- **Not pleated**: Ruffle is soft and flouncy; pleated is crisp
- **Applied strip**: Ruffle is separate piece attached

---

*Cut strip, gather edge, attach. The flounce is the frill.*
