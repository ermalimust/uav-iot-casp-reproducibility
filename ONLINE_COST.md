# Online-cost-v1 archive and local reproduction

Download [online-cost-v1-20261009.zip](artifacts/online-cost-v1-20261009.zip) (383567 bytes; SHA-256 `4c98732a20fb08e7caffe2106af977ff17b9c2e9ed67be50cbf281a67d07e2d4`). This is one small separate companion, with 90 archive members. [VERSION_ONLINE_COST.json](VERSION_ONLINE_COST.json) binds every member and [REPRODUCTION_ONLINE_COST.json](REPRODUCTION_ONLINE_COST.json) records the actual fresh extraction and four byte-identical saved-report outputs. Preparation/local reproduction alone does not establish anonymous public availability.

# Current online structural repair-loop cost: saved evidence

`online-cost-v1-20261009` is a separate, prespecified **current cost illustration** for this paper. It retains all S1--S4 tasks at seeds 1--3, with one fresh online request in each task: 12 completed requests, zero retries/probes, and all 12 final portfolios passing their service contract. These twelve tasks do not constitute a new effectiveness comparison, reconstruct historical model latency, or establish a deployment deadline or population p95 guarantee. They do not change the original study's admission results. This companion is separate from the original-study archives, the eight-volume saved-evidence extension, and the 117-volume native study/121 native release assets.

The measured host was the existing Intel Core i7-9700 (nominal 3.0 GHz), Windows 10, 15.9 GiB physical RAM and Python 3.12.14, with one sequential parent and a fresh worker per task. This was the same machine used for the original local-cost profile. No new dependency installation is implied. The completed execution made 759 candidate calibration evaluations plus 12 nominal diagnosis evaluations (771 simulator calls), with zero simulation-cache hits. It retained the original raw grid order, repeated candidates, first passing candidate rule and portfolio promotion; the numerical bound is 120 candidate evaluations per task, not a claim that every task consumed that bound.

The current requests used the DashScope OpenAI-compatible endpoint and requested alias `qwen-plus`, temperature 0.2, `max_tokens=1024`, `enable_thinking=false`, one nonstreamed response per request. All returned model fields also identify `qwen-plus`; no fixed provider snapshot/version or system fingerprint was supplied. These metadata cannot establish that the physical backend matches the historical alias. Actual reported usage was 3,871 prompt + 1,053 completion = 4,924 total tokens; all twelve raw responses report zero cached prompt tokens. No monetary bill is inferred. The original protocol's preparation-time status is retained as provenance; `saved_live/completion.json` records this actual completed execution.

| Measured interval | Median (s) | Sample p95 (s) | Range (s) |
|---|---:|---:|---:|
| Request/response transport call | 2.346 | 2.777 | 2.069--2.845 |
| Local stages | 3.824 | 4.107 | 1.003--4.219 |
| Numerical calibration | 3.742 | 4.021 | 0.922--4.130 |
| Diagnosis to promotion | 6.268 | 7.128 | 3.695--7.298 |
| Worker startup to exit | 6.747 | 7.543 | 4.121--7.675 |

These intervals are nested and must not be added. Quantiles use linear interpolation at sorted index `(n-1)*q` and describe only these twelve retained tasks. The request timer covers the transport function: payload encoding and request construction, verified direct connection/DNS/TLS, service/generation, and response transfer/handling; it is not pure model compute. Diagnosis-to-promotion wall time starts before nominal diagnosis and stops after promotion. It includes the online request, response JSON decoding, and `request_before`, `response_raw`, `request_after` persistence (JSON writing, flush, fsync and publication). It excludes worker startup/import/preparation, the final `cell.json` artifact writing, the subsequent promotion deepcopy, and energy postprocessing (disabled in this execution). Local stages sum diagnosis, prompt, parser, calibration and promotion only; they exclude HTTP and request-persistence overhead. Parent-observed worker wall includes startup/preparation, final cell-artifact writing and exit.

The package contains 64 exact live scientific record files: manifest/preparation/completion/summary, twelve worker records and all 48 cell/request/raw artifacts. `sources/` preserves all 17 SHA-pinned source/reference inputs, including the original protocol JSON/Markdown and historical reference CSV/cache, exactly as bound by the live preparation. `PATH_MAP.json` maps their historical absolute provenance paths to these package-relative copies. Those absolute strings are passive metadata; the offline command never opens an old scientific tree. Historical source entry points and launch code are retained for provenance, and are not the offline command.

`tools/report_original_structural_online_cost.py` is an exact copy of the standard-library saved-record reporter. `expected_report/` contains its four archived v2 output files, with the LF portable text form fixed by the original report preparation. The CSV retains its original CSV writer byte convention. `MANIFEST.json` inventories every package member and hashes every payload file; the manifest itself is bound by the published archive SHA and external package receipt, avoiding a self-hash cycle.

From the fresh extracted `online-cost-v1-20261009` directory, run with **Python 3.12 or later**, without third-party packages:

```text
python -I -S -B verify_and_report_saved_online_cost.py --output ../offline-online-cost-check-001
```

Choose a different fresh output name if that path already exists. The verifier checks the complete member set and every payload SHA/size, the exact 17 source copies against original preparation and final source identities, all 48 completed request artifacts, the original reporter source/import scope, and the four archived outputs. It then invokes the unchanged reporter once on package-relative saved records and compares all four new outputs byte for byte. It checks the full package unchanged afterwards and writes logs plus `OFFLINE_CHECK_RECEIPT.json` outside the package. Failures preserve the first attempt without repair or retry. This action only analyzes saved records; it makes no model/network request, reads no credential/configuration, imports no experiment runner, and executes no simulator, native backend or energy calculation.

No local authorization, launch reservation/claim, PID control record, private network check, credential/configuration file, manuscript or reviewer document is included. Hash references to omitted administrative controls remain inside exact original manifests as passive provenance; they do not authorize another live run. Preserve existing source attribution and third-party terms; this companion adds no separate code reuse license.
