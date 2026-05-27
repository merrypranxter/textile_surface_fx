# Textile Surface Effects

Velvet nap. Corduroy ribs. Chenille fuzz. Sequin sparkle.

This repository documents textile material microstructure — **how light interacts with cloth surface** through pile, fuzz, rib, sheen, and coating.

## The Core Principle

Surface effects are **BRDF problems with microgeometry**. The weave or knit structure is secondary; what matters is how fibers, threads, and coatings interact with light.

- **Pile**: Fibers standing perpendicular to fabric surface (velvet, corduroy, terry)
- **Fuzz**: Loose fiber ends creating halo (fleece, bouclé, tweed)
- **Rib**: Raised parallel ridges (corduroy, ottoman, repp)
- **Sheen**: Specular reflection from thread surface (silk, satin, lamé)
- **Coating**: External layer bonded to fabric (flock, foil, rubberized)
- **Transparency**: Light passing through (organza, mesh, burnout)

## The Surface Families

### Pile Fabrics
- [Velvet](pattern_families/velvet.md) — cut pile, directional nap, stroke-sensitive
- [Corduroy](pattern_families/corduroy.md) — cut pile in ribs/wales, directional
- [Terry cloth](pattern_families/terry.md) — loop pile, absorbency geometry
- [Chenille](pattern_families/chenille.md) — fuzzy pile yarn, soft texture
- [Velour](pattern_families/velour.md) — stretch velvet, knit-backed
- [Plush](pattern_families/plush.md) — long pile, toy/blanket fabric

### Fuzz / Texture Fabrics
- [Fleece](pattern_families/fleece.md) — brushed synthetic, matte halo
- [Bouclé](pattern_families/boucle.md) — looped yarn, nubby texture
- [Tweed](pattern_families/tweed.md) — mixed color slubs, irregular texture
- [Felt](pattern_families/felt.md) — matted fibers, non-woven, dense
- [Raw silk / dupioni](pattern_families/raw_silk.md) — slubs and irregularity

### Reflective / Metallic
- [Lamé](pattern_families/lame.md) — metallic thread woven in
- [Sequined fabric](pattern_families/sequined.md) — disc attachments, high sparkle
- [Holographic fabric](pattern_families/holographic.md) — iridescent film coating
- [Foil print](pattern_families/foil_print.md) — metallic transfer on surface

### Transparent / Mesh
- [Organza](pattern_families/organza.md) — sheer, crisp, slight sheen
- [Tulle](pattern_families/tulle.md) — fine net, ballet skirt fabric
- [Mesh](pattern_families/mesh.md) — open grid, sportswear
- [Burnout / devoré](pattern_families/burnout.md) — selective fiber destruction
- [Burnout velvet](pattern_families/burnout_velvet.md) — pile + sheer ground

### Coated / Bonded
- [Flocked fabric](pattern_families/flocked.md) — adhesive + short fibers
- [Rubberized](pattern_families/rubberized.md) — rubber coating, waterproof
- [Waxed canvas](pattern_families/waxed_canvas.md) — wax impregnation, patina
- [Laminated](pattern_families/laminated.md) — film bonded to fabric

### Ribbed / Woven Texture
- [Ottoman](pattern_families/ottoman.md) — heavy crosswise rib
- [Repp](pattern_families/repp.md) — fine crosswise rib, corded surface
- [Faille](pattern_families/faille.md) — subtle rib, slight sheen
- [Grosgrain](pattern_families/grosgrain.md) — heavy rib, ribbon fabric
- [Poplin](pattern_families/poplin.md) — fine crosswise rib, shirting

### Distressed / Worn
- [Distressed denim](pattern_families/distressed_denim.md) — abrasion, whiskers, holes
- [Worn velvet](pattern_families/worn_velvet.md) — crushed, patchy nap
- [Vintage cotton](pattern_families/vintage_cotton.md) — fade, softening, edge wear

## Shader Translation: Surface FX Parameters

| Parameter | What It Controls | Range | Notes |
|-----------|---------------|-------|-------|
| `pile_height` | Fiber standoff from ground | 0.0–0.5 | 0 = flat, 0.5 = plush |
| `nap_direction` | Pile lean angle | 0°–180° | Affects anisotropic BRDF |
| `nap_uniformity` | How aligned fibers are | 0.0–1.0 | 1.0 = velvet, 0.0 = frizzy |
| `fuzz_radius` | Halo scatter distance | 0.0–0.3 | Fleece/bouclé effect |
| `rib_frequency` | Ridges per unit | 5–100 | Corduroy wale count |
| `rib_depth` | Height of ridge | 0.0–0.2 | Normal displacement |
| `specular_power` | Shininess | 1.0–128.0 | 1 = matte, 128 = mirror |
| `metallic_tint` | Metal color | RGB | Gold, silver, copper |
| `sparkle_density` | Sequin/glitter particles | 0–1000 | Per unit area |
| `transparency` | Light transmission | 0.0–1.0 | 0 = opaque, 1 = clear |
| `coating_thickness` | Surface layer depth | 0.0–0.1 | For flock/rubber |

## Surface-to-Shader Logic

### Velvet Anisotropic BRDF
```glsl
float velvet_brdf(vec3 view, vec3 light, vec3 normal, float nap_angle) {
    vec3 nap = rotate(normal, nap_angle);
    float cos_nap_view = dot(nap, view);
    float cos_nap_light = dot(nap, light);
    float aniso = pow(max(cos_nap_view, 0.0), specular_power);
    float retro = pow(max(cos_nap_light, 0.0), retro_power);
    return aniso * retro;
}
```

### Corduroy Rib Normal
```glsl
vec3 corduroy_normal(vec2 uv, float freq, float depth) {
    float rib = sin(uv.x * freq * PI);
    vec3 normal = normalize(vec3(rib * depth, 0.0, 1.0));
    return normal;
}
```

### Fleece Fuzz Halo
```glsl
float fleece_fuzz(vec3 view, vec3 normal, float fuzz_amount) {
    float fresnel = pow(1.0 - abs(dot(view, normal)), 2.0);
    return fresnel * fuzz_amount;
}
```

## Prompt Templates

### Velvet
> "Deep [COLOR] velvet with directional nap, photographed with raking light from [DIRECTION], showing stroke-sensitive sheen where fibers catch light, crushed areas darker, plush texture"

### Corduroy
> "Wide-wale corduroy in [COLOR], showing distinct vertical ribs with soft pile between valleys, directional light catching ridge tops, cotton fabric, garment detail"

### Sequined
> "Dense sequin fabric on mesh backing, [COLOR] sequins catching point light sources with star-shaped specular highlights, slight overlap of disc edges, stage costume material"

## Anti-Drift: Surface FX Specific

- **Velvet vs velour**: Velvet = woven cut pile; velour = knit-backed, stretchier
- **Corduroy wale count matters**: 4-wale = wide ribs; 16-wale = fine pinwale
- **Lamé vs foil**: Lamé = metallic thread woven in; foil = metallic layer on surface
- **Burnout vs devoré**: Same technique; devoré is the French term
- **Flock is not velvet**: Flock = adhesive + short fibers; velvet = cut pile from woven base
- **Mesh vs tulle**: Mesh = synthetic open grid; tulle = fine hexagonal net, often stiffer

---

*This repo treats surface effects as BRDF problems. The fiber is the geometry. The light is the equation. The eye is the solver.*
