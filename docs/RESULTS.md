# Validation results

All temperature errors below are in degrees Celsius. Mean-depth RMSE is the arithmetic mean of the per-depth RMSEs, rather than a pooled error across all rows.

## Repaired matched evaluation

**2023–24 delayed-mode Argo · 96 floats · 69,183 support-verified rows**

| Comparator | OceanVision | Reference | Point wins | Simultaneously supported depths |
|---|---:|---:|---:|---:|
| INCOIS | **0.6778** | **0.8554** | **14/14** | **10/14** |
| GLORYS12, physically aligned | 0.6885 | 0.7009 | 8/14 | 3/14 |

Each comparator uses its own eligible matched observations, so the two OceanVision values are not interchangeable. INCOIS starts at 5 m; its 14-depth comparison does not validate the 0 m output.

The INCOIS mean-depth RMSE reduction is **20.8%**. Four of the 14 point wins do not have simultaneous uncertainty support. The inspected development benchmark is not an untouched future evaluation.

## Independent Argo validation

| Separate development lineage | Score |
|---|---:|
| Independent Argo monitor | **0.7271** |
| GLORYS validation, different target | **0.6262** |

This lineage uses GLORYS-only training, model selection and early stopping. Argo is a monitoring dataset in this audit. The deployed model is a separate lineage that uses earlier Argo observations for calibration and selection. Both use surface inputs at inference.

The two numbers in this table answer different validation questions. They cannot be used to claim a paired win against GLORYS12.

## Historical evaluation

| Window and protocol | OceanVision | GLORYS12 | Point wins |
|---|---:|---:|---:|
| Jul–Dec 2025 delayed-mode, earlier protocol | 0.5547 | 0.5927 | 12/15 |

This result predates the final observation-pipeline repairs. It is retained as historical evidence and does not independently confirm the final repaired model.

The frozen-representation evaluation reports **R² 0.4749**, versus **0.4272** for equal-width PCA. This is a representation metric, separate from temperature RMSE.

## Interpretation

The repaired INCOIS comparison supports lower measured RMSE at all 14 shared depths, with simultaneous support at 10. The GLORYS12 result has an aggregate advantage but does not establish an all-depth win. The original 2026 confirmation claim was withdrawn after an observation and artifact audit. No replacement untouched future test is claimed.

Published numerical records are summarized in [results.json](results.json). The values were carried forward from the audited project release; this repository creation is not a new scoring run. The live [validation page](https://oceanembed-prototype.vercel.app/#/validation) provides the public result tables.
