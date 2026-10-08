# UAV-IoT CASP reproducibility

Reproducibility materials for **Validated Recoverability for Heterogeneous-Protocol
Single-UAV IoT Service Policies**.

The versioned archives preserve the original study's code, seed records,
candidate histories, backend caches, and external-anchor inputs. The repository
publication receipt identifies the actual public commit and archive SHA-256
digests. Preparation and clean-extraction checks alone do not establish public
availability.

## Original-study snapshots

| Archive | Scope | SHA-256 |
|---|---|---|
| `artifacts/publication_original_core_v1_20261008.zip` | Original simulator, contract records, controlled experiments, cached model evidence, and strict S1–S4 replay entry point | `159b421881fdfa61c30027f85d764d968fa3935ea67cb6193df90352a14872be` |
| `artifacts/publication_original_complements_public_v1_20261008.zip` | PPO code/checkpoint, blackout postprocessor, missing reduced ns-3 source/results, and AERPAW extraction code/data | `5b11d91248ff1ae108f9203a2cf3dad4dbbf4815a94940b259f2d47fb05e2b1b` |

Extract both archives into the **same fresh directory**. Their scientific and
administrative paths do not overwrite one another. Preserve the original paths;
the complementary manifest binds the exact core manifest. The archive READMEs
retain preparation-time context; use the dependency and execution instructions
below for reproduction.

## Verify and replay without a model request

From the merged extraction:

```text
python -I -S -B verify_artifact.py
python -I -S -B original-complements-v1/verify_artifact.py --root .
```

Both hash verifiers use only the Python standard library. The core verifier
also recovers the structural admission counts from the frozen seed ledger.

The tested extraction host used Python 3.12, Pillow 12.3.0, NumPy 2.3.5, and
pandas 3.0.1. These are recorded host versions, rather than a newly installed
dependency-environment test. **Pillow is required** by the original simulator's
imports; NumPy/pandas support other numerical postprocessors. Plotting requires
matplotlib separately. The original core archive's shorter dependency note is
superseded by this clarification.

A small actual numerical reproduction is:

```text
python -B revision/experiments/measure_original_structural_costs.py --seeds 1:1 --out reproduction_smoke
```

This executes S1–S4 and the three original portfolios in 12 cells, using saved
model responses, original raw calibration grids, first-pass rules, and final
promotion. It makes **zero model requests** and refuses to overwrite its output.
Use `--seeds 1:100` with a different fresh output directory for all 400 instances
and 1,200 cells. New timings depend on the reproduction host and do not recreate
historical online model latency.

Generic legacy model clients can attempt live requests or synthetic fallback
when a cache is missing; some old entry points also require key presence. They
are preserved as source provenance. Supplying a cache alone does not make every
legacy entry point a strict offline runner. Use the checked entry point above;
its cached-model selection rejects a missing or inconsistent prompt identity.

## External anchors and PPO

The complement preserves the original AERPAW subset: 33 LoRa flight logs and two
processed USRP CSVs. The input data come from the [AERPAW AADM Dryad
dataset](https://datadryad.org/dataset/doi%3A10.5061/dryad.7d7wm3898), under
Dryad's [CC0 data policy](https://datadryad.org/mission). Dataset attribution and
its original README accompany the subset. These are previously used public
measurements, rather than new CASP hardware tests.

Let `E` be the retained directory
`ZQL_UAV_submission_260708/02_復現_GitHub公開包/02_EVIDENCE_AND_EXPERIMENTS/02_EVIDENCE_AND_EXPERIMENTS`.
From `E`, the two standard-library extractions are:

```text
python -I -S -B experiments/real_trace_anchor/scripts/extract_lora_anchor.py --input experiments/real_trace_anchor/data/raw/aerpaw_aadm/extracted --out-dir reproduction_lora
python -I -S -B experiments/real_trace_anchor/scripts/extract_usrp_anchor.py --input experiments/real_trace_anchor/data/raw/aerpaw_aadm/extracted --out-dir reproduction_usrp
```

Fresh extraction reproduced the four original summary JSON/metric CSV files
byte for byte. The plot script is included, but plotting was not repeated in
this clean check.

The PPO checkpoint is `experiments/uav_iot_workflow/results/ppo_4m.zip` under
`E`. Its metadata records stable-baselines3 2.8.0 and 4,001,792 actual steps for
the 4M training target. Loading it requires the original environment plus
gymnasium, stable-baselines3/PyTorch, NumPy, and pandas. The old PPO CLI defaults
to retraining; it is not a checkpoint-evaluation command. The checkpoint was
preserved and inspected as an archive, but was not loaded, retrained, or
evaluated during this clean check.

The included old ns-3.47 sources and outputs are reduced two-node anchors. The
original runners require a separate ns-3 runtime and were not rerun in the
complement check. They must not be identified as the new full multi-node CASP
extension.

## Evidence and reuse boundaries

The canonical study uses normalized service profiles and 30 stationary devices.
Contract admission is relative to the evaluated inputs, observers, and finite
contingencies. A cached model alias identifies a historical response source;
it does not guarantee a provider's present model version. Numerical replay and
public-trace extraction do not establish flight safety or deployment deadlines.

Energy screening, neighboring contract predicates, fresh online latency, and
the new full-native extension are separate revision artifacts. These original
snapshots do not claim to contain or validate all those extensions. No API key,
private configuration, reviewer report, response document, or manuscript is
included. No additional reuse license is granted for the authors' code; preserve
existing attribution and third-party terms.
