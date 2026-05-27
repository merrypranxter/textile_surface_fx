# Lace Texture

Openwork surface. Delicate grid.

## What It Is

Lace as a surface texture refers to **openwork fabric with deliberate holes** creating a decorative pattern. The texture comes from the combination of solid and open areas.

## Construction

- **Knitted, woven, or crocheted**: Various lace-making methods
- **Open holes**: Gaps are intentional design element
- **Solid motifs**: Filled areas create contrast
- **Fine thread**: Usually very thin yarn or thread

## Visual DNA

- **Visible holes**: Open areas are part of design
- **Delicate structure**: Fine thread, fragile appearance
- **Patterned openwork**: Holes form specific motifs
- **Sheer quality**: Light passes through open areas
- **Common uses**: Bridal, lingerie, tablecloths, curtains, overlays

## Shader Parameters

| Parameter | Range | Notes |
|-----------|-------|-------|
| `openness` | 0.2–0.8 | Percentage of holes |
| `motif_complexity` | 0.3–1.0 | Pattern intricacy |
| `thread_fineness` | 0.001–0.005 | Very thin threads |
| `sheerness` | 0.3–0.9 | Light transmission |

## GLSL Snippet

```glsl
float lace_texture(vec2 uv, float openness) {
    float solid = lace_pattern(uv, scale);
    float holes = 1.0 - solid;
    float sheer = holes * sheerness;
    return solid + sheer;
}
```

## Prompt Template

> "Lace fabric in [COLOR], openwork [MOTIF] pattern with deliberate holes and solid motifs, delicate fine thread, sheer elegant textile"

## Anti-Drift

- **Not mesh**: Lace has decorative holes; mesh is uniform grid
- **Not cutwork**: Lace is constructed openwork; cutwork is cut from solid
- **Fine thread**: The delicacy is part of the definition

---

*Hole and solid, pattern in both. The absence is the design.*
