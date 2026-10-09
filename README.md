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

## Revision saved-evidence extension

The separate **revision-evidence-v1** snapshot contains the complete saved local-cost, fixed-policy energy, and predicate-neighborhood evidence. Download **all eight volumes** below and extract them into the same fresh directory. The original-study archives above remain unchanged.

| Volume | Bytes | SHA-256 |
|---|---:|---|
| [revision-evidence-v1-fixed-policy-energy-analysis-01.zip](artifacts/revision-evidence-v1-fixed-policy-energy-analysis-01.zip) | 4,568,403 | `b60a193cc829d2d4e198f7a2a281670147d20c81656192956f6eab7ce42739a3` |
| [revision-evidence-v1-fixed-policy-energy-records-01.zip](artifacts/revision-evidence-v1-fixed-policy-energy-records-01.zip) | 74,866,589 | `df4c9e31e42563cfd27031aa84a2abf2fdd506a6f815859d6fff2b827d1cca8c` |
| [revision-evidence-v1-fixed-policy-energy-records-02.zip](artifacts/revision-evidence-v1-fixed-policy-energy-records-02.zip) | 74,893,477 | `14126549ec5580b872df8ab8c692ef1074ce50e5f08c673b9e13466fb6449ad7` |
| [revision-evidence-v1-fixed-policy-energy-records-03.zip](artifacts/revision-evidence-v1-fixed-policy-energy-records-03.zip) | 2,269,931 | `55e7a01135c38e54df795b748e1762956313fd000e42ed7162788ecaff87d601` |
| [revision-evidence-v1-local-cost-analysis-01.zip](artifacts/revision-evidence-v1-local-cost-analysis-01.zip) | 112,197 | `d470bf492a79b75649576d592e05e9907d4be3014bafecd66846bc32c08cd4b1` |
| [revision-evidence-v1-local-cost-records-01.zip](artifacts/revision-evidence-v1-local-cost-records-01.zip) | 9,418,825 | `0f7d4ea9d0d58cc14902b012d8a214dfcf847e573e432e0edff468f1c26405d6` |
| [revision-evidence-v1-predicate-neighborhood-analysis-01.zip](artifacts/revision-evidence-v1-predicate-neighborhood-analysis-01.zip) | 1,310,951 | `9b6ad37d95cb06fdcaf40d274efebfb4a964356488a2e78e25abe0f8f8ed3fa5` |
| [revision-evidence-v1-shared-code-and-dependencies-01.zip](artifacts/revision-evidence-v1-shared-code-and-dependencies-01.zip) | 1,500,256 | `df073edf02c3ec91ebdc1c4d06041034ca3ed055df0a6f3d976714ee510eb703` |

See [REVISION_EVIDENCE.md](REVISION_EVIDENCE.md) for extraction, verification, and the seven standard-library saved-evidence actions. The shared volume includes the required original-core dependency snapshot; its preserved root README describes the older core only. Use the extension instructions for these checks.

Fresh extraction completed all seven actions and reproduced 27 analysis files: 23 byte-identical CSV/TeX/Markdown files and four exact JSON results after only historical-root normalization and two creation timestamps. [REPRODUCTION_REVISION_EVIDENCE.json](REPRODUCTION_REVISION_EVIDENCE.json) records that local evidence; actual anonymous publication identity is recorded separately. Archive preparation-time wording is retained as provenance, rather than a statement about current repository availability.

This extension does not include the full-native formal raw, fresh online/compositional experiments, or S/B interface diagnostics. It does not measure new online latency or validate a flight controller.

## Complete native CASP study

The complete 31-node packet-level study is available in the
[native-formal-v1-20261008 release](https://github.com/ermalimust/uav-iot-casp-reproducibility/releases/tag/native-formal-v1-20261008).
Its **117 formal volumes** retain all 48,402 inventoried files for 40 matched
instances, 120 arm records and 7,960 native evaluator calls. Download the
release's `README-native-formal-v1.md`, `RELEASE_ASSETS.json`,
`native-formal-v1-tools-and-local-checks.zip` and all 117 formal volumes.
The automatically generated source-code ZIP/TAR does not include these volumes.

Complete fresh-directory outer, packet-ledger and summary checks passed using
the unchanged scientific modules. The guide records the tested environment,
exact administrative differences and commands for reproducing these checks
without new simulator or model execution. The optional
`sender_diagnostic_public_candidate_v1.zip` is supplied separately; its finite
check covers 16 saved R4 records and the two saved-reading tables.

All **121 release assets** were downloaded without authentication and verified,
including every formal archive member, all 74 tools members and all 404 sender
companion members. See [PUBLICATION_NATIVE_FORMAL.json](PUBLICATION_NATIVE_FORMAL.json)
and [ANONYMOUS_NATIVE_FORMAL_BYTES.json](ANONYMOUS_NATIVE_FORMAL_BYTES.json).
These receipts establish public saved-byte identity; the release guide states
the scientific scope and the distinction from a new deployment observation.

## Current online cost illustration

The separate [online-cost-v1-20261009 companion](ONLINE_COST.md) retains the
prespecified twelve current online tasks, their complete saved records, exact
source provenance, and a standard-library offline cost reporter. It made twelve
fresh model requests with zero retries/probes and records 759 candidate plus 12
nominal evaluations, with 4,924 reported tokens. Diagnosis-to-promotion median
and sample p95 were 6.268 and 7.128 seconds on the recorded host, including
request/response persistence and excluding worker startup/preparation and final
cell-artifact writing. These twelve tasks are a current cost illustration, not
a new effectiveness comparison or a deployment deadline/tail guarantee.

The archive is separate from the 117 formal native volumes and 121 native
release assets. Fresh local extraction verified all 90 members and reproduced
all four saved-record reports byte for byte, with no model or simulator run.
See [VERSION_ONLINE_COST.json](VERSION_ONLINE_COST.json) and
[REPRODUCTION_ONLINE_COST.json](REPRODUCTION_ONLINE_COST.json) for identities and
the tested offline scope. The existing study archives remain unchanged.

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
