# Revision evidence v1: complete saved-evidence extension

This extension contains the complete local-cost, fixed-policy energy, and predicate-neighborhood records, analysis files, byte-identical scientific sources, inputs, historical independent audits, and a root-mapping entry point. All eight volumes below are required for the complete checks. The shared volume contains the original-core dependency snapshot. The original-core root `README.md` and `MANIFEST.json` are preserved for identity; this file is the extension's current extraction and verification entry point.

## Extract all eight volumes into one clean root

- `revision-evidence-v1-fixed-policy-energy-analysis-01.zip`
- `revision-evidence-v1-fixed-policy-energy-records-01.zip`
- `revision-evidence-v1-fixed-policy-energy-records-02.zip`
- `revision-evidence-v1-fixed-policy-energy-records-03.zip`
- `revision-evidence-v1-local-cost-analysis-01.zip`
- `revision-evidence-v1-local-cost-records-01.zip`
- `revision-evidence-v1-predicate-neighborhood-analysis-01.zip`
- `revision-evidence-v1-shared-code-and-dependencies-01.zip`

The eight ZIP files together occupy approximately 169 MB; each individual ZIP is below 80,000,000 bytes. Extraction requires approximately 1.23 GB before producing fresh analysis outputs. Preserve every relative path. For example, from a directory containing all eight volumes, Windows PowerShell with Python on PATH can extract them as follows:

```powershell
$volumes = @(
  "revision-evidence-v1-fixed-policy-energy-analysis-01.zip",
  "revision-evidence-v1-fixed-policy-energy-records-01.zip",
  "revision-evidence-v1-fixed-policy-energy-records-02.zip",
  "revision-evidence-v1-fixed-policy-energy-records-03.zip",
  "revision-evidence-v1-local-cost-analysis-01.zip",
  "revision-evidence-v1-local-cost-records-01.zip",
  "revision-evidence-v1-predicate-neighborhood-analysis-01.zip",
  "revision-evidence-v1-shared-code-and-dependencies-01.zip"
)
New-Item -ItemType Directory -Path .\revision-evidence-v1-extracted
foreach ($name in $volumes) {
  python -m zipfile -e $name .\revision-evidence-v1-extracted
  if ($LASTEXITCODE -ne 0) { throw "Extraction failed: $name" }
}
Set-Location .\revision-evidence-v1-extracted
python -B revision-evidence-v1/portable_reproduce_revision_evidence.py --root . --action verify
```

The entry point validates every inventoried file's raw size and SHA-256 before using it. Its only compatibility adjustment maps the recorded historical repository root to the extracted root; scientific sources and raw records remain unchanged. The new extension manifest is `revision-evidence-v1/MANIFEST.json`.

## Check and recompute saved evidence

Use the same entry point with any of `cost-audit`, `energy-audit`, `cost-summary`, `energy-summary`, `predicates`, or `predicate-audit`, and a new output directory outside the extracted package. For example:

```powershell
python -B revision-evidence-v1/portable_reproduce_revision_evidence.py --root . --action cost-audit --out ../cost-audit-fresh
python -B revision-evidence-v1/portable_reproduce_revision_evidence.py --root . --action energy-audit --out ../energy-audit-fresh
python -B revision-evidence-v1/portable_reproduce_revision_evidence.py --root . --action cost-summary --out ../cost-summary-fresh
python -B revision-evidence-v1/portable_reproduce_revision_evidence.py --root . --action energy-summary --out ../energy-summary-fresh
python -B revision-evidence-v1/portable_reproduce_revision_evidence.py --root . --action predicates --out ../predicates-fresh
python -B revision-evidence-v1/portable_reproduce_revision_evidence.py --root . --action predicate-audit --out ../predicate-audit-fresh
```

These actions check or recompute saved records and independent accounting. They perform no simulation, model request, API-key access, or new effectiveness measurement. Output directories must not already exist; choose a fresh sibling for another intentional check. Original historical audits remain in the package and fresh checks are written separately.

## Dependencies and actual tested scope

The seven actions above (including `verify`) use only the Python standard library. They were actually run from a fresh extraction with Python 3.12.14 (64-bit AMD64, MSC v.1944) on Windows 10 build 19045. NumPy 2.3.5 and Pillow 12.3.0 were installed in that environment but were not imported or required by these saved-evidence actions; Matplotlib was not installed. The original-core controller runner and figure-producing tools have separate dependencies, including Pillow in the original runner, and were not rerun in this check. This is a tested Windows fresh-root path-mapping result; Linux, macOS, other Python versions, physical simulations, and controller reruns have not been established by this package check.

The first fresh extraction completed all seven actions: 1,200 local-cost cells with 524,956 audit assertions; 1,200 energy cells, 9,600 profiles, 144,000 gates, and 2,546,704 endpoints with 30,722,552 audit assertions; and 1,200 fixed policies, 36,000 device records, 72,000 predicate readings, and 60 conditions with 518,650 independent checks. Recomputed analysis matched 23 CSV/TeX/Markdown files byte-for-byte and four JSON outputs in exact values/types after only recorded-root path normalization and removal of two summary creation timestamps. The later README/manifest administrative copy changed no scientific file or tested entry point and underwent fresh extraction and identity verification only; the mathematical results were not rerun for that copy.

## Scientific interpretation and remaining coverage

Local-cost timing/memory values are historical host measurements, not fresh timings or online model latency. Energy results use the stated ideal horizontal quasi-steady fixed-trajectory model and eight predeclared profiles/120 conditions; they are not flight or return-controller validation. Predicate results preserve all fixed policies and their service-derived records without adding a controller experiment.

The full native formal raw, fresh online/compositional experiments, and S/B interface diagnostics are not included. Their publication and reproducibility status must be stated separately. This candidate remains local pending publication review; its preparation does not establish public GitHub availability. No new license is granted; existing source attribution and third-party terms apply.
