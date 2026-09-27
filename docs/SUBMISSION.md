# OceanVision submission brief

**Team ZenTechs · Team ID 130957 · SIH 2026 · PS SIH26066 · Ministry of Earth Sciences / INCOIS**

| Resource | Link |
|---|---|
| Prototype | https://oceanembed-prototype.vercel.app/ |
| Pitch video | https://youtu.be/BSgT3coOmeM |
| Project showcase | https://github.com/devanshranjan10/OceanVision |
| Validation results | https://oceanembed-prototype.vercel.app/#/validation |

## Problem

Surface satellite observations cover the ocean much more densely than subsurface measurements. OceanVision uses surface observations to reconstruct the temperature column, giving users a daily spatial view of subsurface conditions.

## Delivered prototype

| Item | Delivered |
|---|---|
| Region | North Indian Ocean, 5–30°N and 45–105°E |
| Grid | Daily, 0.25°, 101 × 241 cells |
| Output depths | 0, 5, 10, 20, 30, 50, 75, 100, 125, 150, 200, 300, 500, 700, 1000 m |
| User outputs | Temperature maps, point profiles, a 3D column and an ocean representation |
| Available archive | 1993-01-01 through 2025-12-31 |

## Validated performance

On the repaired 2023–24 delayed-mode Argo benchmark, OceanVision scores **0.6778°C** mean-depth RMSE versus **INCOIS 0.8554°C**. The difference is **20.8%**, with lower point-estimate RMSE at **14/14 shared depths** and simultaneous uncertainty support at **10/14**. The benchmark has **96 floats and 69,183 support-verified rows**.

The physically aligned GLORYS12 comparison uses a separate matched sample: **OceanVision 0.6885°C versus GLORYS12 0.7009°C**, with 8/14 point wins and 3/14 simultaneously supported depths.

The independent Argo monitor for the separate GLORYS-only development lineage scores **0.7271°C**. That lineage's GLORYS validation score, **0.6262°C**, uses a different target and is not a paired comparator result.

[RESULTS.md](RESULTS.md) records historical scores and the validation boundaries. The deployed model uses earlier Argo observations for calibration and selection, while using surface inputs at inference. The 2023–24 benchmark was inspected during development. These results do not establish universal regional SOTA or future all-depth superiority.

This submission showcase does not distribute implementation details, reproducible training recipes, checkpoints or datasets.
