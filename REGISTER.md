# The studies behind the September 2026 evidence packs

Eleven feasibility studies, company-funded by Numberz.ai Inc. in August and September 2026, each published as its own repository. This file says what each one is, what it can and cannot support, and how to run it. It is the published companion to `CROSS_HOST_2026-09-16.md`, which records what reproduced across machines and what did not.

Every study follows the same layout. `code/reproduce.sh` regenerates every number from source; `results/` holds one hashed JSON per experiment; `results/manifest.json` records the host, the library versions, the seed and a run identifier that is the first 16 hex digits of a SHA-256 over the source and corpus digests; `RUN_RECORD.md` lists every run, including the ones that exited non-zero. A reader who clones a repository and reproduces its identifier has reproduced the tree the results came from.

## The studies

| Study | Repository | What the code is | Lines / tests | Needs | Run identifier |
|---|---|---|---|---|---|
| DEBRIEFLINE | [postmission-record-provenance](https://github.com/NumberzRiseAgain/postmission-record-provenance) | A seeded synthetic post-mission corpus (223 sorties, 483 artifacts, 138,148 records) and nine experiments: provenance round trip, cross-format reconciliation, precedence quorum, coverage gate, disambiguation, freshness, overlay, recompute, latency | 790 / 7 | stdlib | `c665267db25f080b` |
| SPOKELINE | [articulation-authority-checks](https://github.com/NumberzRiseAgain/articulation-authority-checks) | An Articulation Authority Set from four surrogate S1000D modules bound to box geometry; six fault classes at 50 trials each against seven deterministic checks; glTF export; a hosted viewer | 1,843 / 5 | stdlib | `346e4b8c6d419337` |
| TORQUELINE | [procedure-authority-validator](https://github.com/NumberzRiseAgain/procedure-authority-validator) | Eight fault classes injected into maintenance work packages and caught by seven checks against a Procedure Authority Set; characterisation of the published S1000D Bike sample; a one-screen Node UI | 1,983 / 6 | stdlib; node for the screen | `58a0a9381295435a` |
| DECKLINE | [ietm-agnostic-viewer](https://github.com/NumberzRiseAgain/ietm-agnostic-viewer) | A format-agnostic IETM viewer over a surrogate corpus of 25 documents in eight formats; six experiments: ingest, marking custody, cross-references, cross-format search, source reconciliation, and PDF and raster paths scored against an authored key | 3,876 / 0 | lxml, Pillow, pdfplumber, pytesseract, tesseract, poppler | `668e8f5e19ffb4c7` |
| SPEEDDIAL | [pathproof-solver-selection](https://github.com/NumberzRiseAgain/pathproof-solver-selection) | Three code bases: solution paths over twelve primitives with path memory and promotion, its demo byte-compared with the locked commit; a pre-registered GP study on a synthetic surrogate; a spectral probe for iterative-solver selection over 432 runs | 4,040 / 59 | stdlib; scipy and scikit-learn for two of the three | `6fe38d1f66c26212` |
| APERTURELINE | [swarm-coherence-boundary](https://github.com/NumberzRiseAgain/swarm-coherence-boundary) | Monte Carlo of the coherent versus non-coherent regime boundary for a four-node X-band swarm, 200,000 trials per point; a two-tight-pairs formation; TikZ figure sources | 3,520 / 149 | numpy, scipy | `69bb344010654ae7` |
| SIGNALCAST | [gated-modulation-recognition](https://github.com/NumberzRiseAgain/gated-modulation-recognition) | A gated modulation-recognition engine (fifteen named features, pre-gate, one learned stage, acceptance gate, evidence record) against a monolithic baseline; a withheld-class sweep; a pre-fix regression | 2,006 / 20 | numpy, scipy, scikit-learn (pinned) | `8292b67d07b231f5` |
| SABER | [hrrp-exchange-policies](https://github.com/NumberzRiseAgain/hrrp-exchange-policies) | A maritime HRRP scene model, four exchange policies with exact bit accounting, evidence fusion and cooperative imaging; E1 to E7 plus E4b; Figure 2 written from the JSON | 1,496 / 23 | numpy, scipy, scikit-learn (pinned) | `cbd19158a1670cc1` |
| CREWLINE | [aircrew-confidence-bound](https://github.com/NumberzRiseAgain/aircrew-confidence-bound) | A pre-registered null on the sqrt-alpha confidence cap (MMASH, 22 subjects), a forced-overconfident control, and the replacement reliability-adjusted evidence bound in closed form, with figure | 877 / 5 | numpy, pandas, scipy, scikit-learn, matplotlib; MMASH from PhysioNet | `d7cad8c2cd7a462e` |
| SISR | [gated-sensing-pipeline](https://github.com/NumberzRiseAgain/gated-sensing-pipeline) | A sensing pipeline (detect, track, stabilise, ground, normality, evidence, emit), a power meter and a low-power kit, run in zero-weights mode | large / 145 tests | numpy, opencv, PyYAML, pytest | `35cb03525a0acaf8` |
| ARRESTLINE | [condition-monitoring-transfer](https://github.com/NumberzRiseAgain/condition-monitoring-transfer) | `cbmx`: loaders for nine public rigs, a physics catalogue, a health baseline and sequential test, an edge bench, 23 tools | large / 5 test files | numpy, scipy, pandas, PyYAML, pytest; public rig datasets by pointer | `e7e85362b5281a30` |

APERTURELINE's identifier moved on 22 September 2026, from `4728293de64cea63` to `69bb344010654ae7`, when E4 (cross-range bounds by measurement set) was added after the partner's review; the repository was republished with a fresh history the same day.

Four identifiers moved on 19 September 2026 when the proposal-time header line in the sources was replaced by the licence line ahead of this release. No result changed; the affected packs are SPOKELINE, TORQUELINE, DECKLINE and SISR, and each repository's README records the earlier value.

## What each study can and cannot say

Every README states its own limits. The short version:

**DEBRIEFLINE.** Measures that typed records round-trip to their source, reconcile across three identifier formats, and that aggregates recompute from the records they cite. The corpus is synthetic and four terms deep, authored by the same firm that wrote the parser, so the result is a property of the implementation and not evidence about any real archive.

**SPOKELINE.** 290 of 300 injected faults caught, 0 of 50 false positives, reproduced exactly on two hosts. The geometry is boxes, so no photogrammetry or model-fidelity claim follows from it.

**TORQUELINE.** 0 of 8 false-positive packages, 53 mutants, per-class F1 to F8 on the seed corpus, and a characterisation of the published Bike corpus at 116 / 39 / 185 / 2. E3, the scored run on that public corpus, is built but gated behind an OSF pre-registration that has not been posted: section 4 of that pre-registration forbids computing the outcome before it is. Until E3 runs, nothing here is a measured result on public data.

**DECKLINE.** Counts identical across four runs on three hosts, the last under tesseract 5.5.3 against 4.1.1 on the earlier ones; only timing moved. The corpus was authored by the parser's author, and the XML and SGML paths are lossless by construction, so the interesting numbers are the OCR ones: worst rights-legend similarity 0.9966 on the scanned raster, and 0 of 3 table rows recovered from it against 6 of 6 and 4 of 4 on digital-native PDFs.

**SPEEDDIAL.** The path layer is a reference implementation with a byte-compared walkthrough and no effect size (33 rows, six problems). The GP study is pre-registered and has never been run on real SWAN-SF partitions. The selector study's headline moves with the scikit-learn version and the shipped artifacts do not record which one produced it, so the number should not be quoted without the version beside it.

**APERTURELINE.** The 4.76 m crossover, the cross-range Cramér–Rao bounds by measurement set (a team keeping its members' angles is never worse than one radar; ranges alone are worse below a 38.3 m baseline), the team-versus-one-radar range 0.43 to 0.94, the 1.4 mm and 9.4 ps tolerance, and the two-pair margin 0.020 to 0.028. Every two-decimal figure survived a second machine; three-decimal figures move by one in the last place, which is the Monte-Carlo floor at 200,000 trials. The correlation model is authored, so the result is a simulation result and stays one until it is measured.

**SIGNALCAST.** The deterministic stages reproduce exactly across stacks, the same 22 off-manifold frames every time. The learned stage does not: correct abstention lands at 0.454, 0.432 or 0.482 depending on the scikit-learn build, and the latency ratio did not hold across machines (3.9x against 2.65x). The corpus is synthetic, AWGN only, no fading, no carrier-frequency offset, no interference. RadioML has not been run.

**SABER.** Seven experiments, including one prediction the study refuted (a 76x rate advantage never exceeds +0.030 anywhere from -4 to 18 dB) and one objection it answered (non-coherent multi-aspect resolution 0.36 m by 0.66 m at four nodes over 90 degrees of aspect). 54 bits reaches 0.890 where 4,126 bits reaches 0.892; image fidelity 0.90 costs 1,054 bits. No external data is involved, so it is a modelling result throughout.

**CREWLINE.** A null: the sqrt-alpha cap moves Brier by +0.003, no construct of eleven reaches significance, and the cap binds on 3 percent of cases. It shows an effect only when a model is forced overconfident at C = 100, where it is +0.069. The bound that replaced it holds worst-case ECE at 0.002 across alpha 0.60 to 0.96 at 200,000 draws. Public dataset, fixed seeds, single-threaded BLAS. Nothing about aircrew is claimed.

**SISR.** Detection, tracking and gating on three synthetic clips with exact ground truth and on staged real footage that is not published here. The power figures come from a meter on a bench, not from an operational edge device. One host difference is on record: the same source tree produced a clip3 link total of 26,856 bits on one Linux machine against 26,928 on two others, which is why the published results name the host that produced them.

**ARRESTLINE.** Nine public rigs, a physics-constrained search, a sequential test and an edge bench. Its own repository states its limits.

## Running one

From any of the repositories:

```
git clone https://github.com/NumberzRiseAgain/<repository>
cd <repository>
pip install -r code/requirements.txt      # where one exists
code/reproduce.sh
```

The script writes `results/*.json`, hashes them into `results/_result_digests.txt`, appends a row to `RUN_RECORD.md` and prints the run identifier. On an unchanged tree that identifier matches the one in the table above. If it does not, something in the source or corpus changed, and the manifest says which file.

Two repositories need data that is not redistributed here: CREWLINE reads MMASH from PhysioNet (`GET_MMASH_DATA.md`), TORQUELINE reads the S1000D Bike sample set (`GET_S1000D_BIKE_DATA.md`). ARRESTLINE fetches nine public rig datasets by pointer, as its own README describes.

## Reproduction across machines

`CROSS_HOST_2026-09-16.md` is the record of running all eleven on a second and third machine. Four classes showed up: bit-identical, last-bit floating point from BLAS and platform, a Monte-Carlo floor within a declared tolerance, and stack-determined, where a learned stage reproduces exactly on the stack that recorded it and moves on another. Timing fields move everywhere and are not quoted from a single host.

## Licence and data

All code here is MIT, copyright 2026 Numberz.ai Inc. No third-party data set is redistributed in any repository; each carries a pointer file for the data it reads. Synthetic and surrogate corpora authored by Numberz.ai are included, and where those carry document markings the markings are test content for the marking-custody experiments, not real distribution statements.
