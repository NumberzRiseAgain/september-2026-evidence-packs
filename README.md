# September 2026 evidence packs

The index of the feasibility studies Numberz.ai Inc. ran for its September 2026 SBIR and STTR submissions, one public repository per study. Each repository is the study's `08_Analysis/` evidence pack: the code, the hashed result files every quoted number comes from, a `RUN_RECORD.md` listing every run including the failed ones, the logs, and a `results/manifest.json` whose run identifier is a SHA-256 over the source digests, so a reader who reproduces the identifier has reproduced the tree. All are MIT licensed; no third-party data set is redistributed.

| Study | Repository | What it measures | Needs |
|---|---|---|---|
| DEBRIEFLINE | [postmission-record-provenance](https://github.com/NumberzRiseAgain/postmission-record-provenance) | nine experiments on a seeded synthetic post-mission corpus: provenance, reconciliation, precedence, coverage, freshness, recompute, latency | stdlib |
| SPOKELINE | [articulation-authority-checks](https://github.com/NumberzRiseAgain/articulation-authority-checks) | an Articulation Authority Set from S1000D modules bound to geometry; six fault classes against seven deterministic checks; glTF export | stdlib |
| TORQUELINE | [procedure-authority-validator](https://github.com/NumberzRiseAgain/procedure-authority-validator) | eight fault classes injected into work packages, seven checks against a Procedure Authority Set; S1000D Bike corpus characterisation | stdlib, node for the screen |
| DECKLINE | [ietm-agnostic-viewer](https://github.com/NumberzRiseAgain/ietm-agnostic-viewer) | a format-agnostic IETM viewer: marking custody, cross-references, cross-format search, source reconciliation, PDF and raster paths against an authored key | lxml, Pillow, pdfplumber, pytesseract, tesseract, poppler |
| SPEEDDIAL | [pathproof-solver-selection](https://github.com/NumberzRiseAgain/pathproof-solver-selection) | solution paths with path memory; a pre-registered GP study on a synthetic surrogate; a spectral probe for iterative-solver selection | stdlib; scipy and scikit-learn for two of the three |
| APERTURELINE | [swarm-coherence-boundary](https://github.com/NumberzRiseAgain/swarm-coherence-boundary) | Monte Carlo of the coherent versus non-coherent regime boundary for a four-node X-band swarm | numpy, scipy |
| SIGNALCAST | [gated-modulation-recognition](https://github.com/NumberzRiseAgain/gated-modulation-recognition) | a gated modulation recogniser with abstention on withheld classes, against a monolithic baseline | numpy, scipy, scikit-learn (pinned) |
| SABER | [hrrp-exchange-policies](https://github.com/NumberzRiseAgain/hrrp-exchange-policies) | maritime HRRP exchange policies with exact bit accounting, evidence fusion, cooperative imaging | numpy, scipy, scikit-learn (pinned) |
| CREWLINE | [aircrew-confidence-bound](https://github.com/NumberzRiseAgain/aircrew-confidence-bound) | a pre-registered null on the sqrt-alpha confidence cap (MMASH) and a reliability-adjusted evidence bound | numpy, pandas, scipy, scikit-learn, matplotlib; MMASH from PhysioNet |
| SISR | [gated-sensing-pipeline](https://github.com/NumberzRiseAgain/gated-sensing-pipeline) | a gated sensing pipeline: detect, track, stabilise, ground, normality, evidence, emit; zero-weights mode | numpy, opencv, PyYAML, pytest |
| ARRESTLINE | [condition-monitoring-transfer](https://github.com/NumberzRiseAgain/condition-monitoring-transfer) | cross-rig condition monitoring: physics catalogue, health baseline, sequential test, edge bench | numpy, scipy, pandas, PyYAML, pytest; public rig datasets by pointer |

## What is here

| File | What it is |
|---|---|
| `REGISTER.md` | what each code base is, what it needs, its run identifier, and what each study can and cannot support |
| `CROSS_HOST_2026-09-16.md` | the cross-host reproduction record: the founder's runs on a MacBook compared leaf by leaf with the cloud runs of record, what reproduced bit for bit, what moved and why |
| `RUN_SUMMARY.md` | one block per run of the whole set, newest last |

## Four classes of reproduction

Observed across the packs on three hosts: bit-identical (stdlib pipelines), last-bit floating point (BLAS and platform), Monte-Carlo floor (within a declared tolerance), and stack-determined (a learned stage that reproduces exactly on the recorded stack and moves on another). Timing fields move everywhere. The cross-host note has the table.
