# paper3-methodology

An 84-Format Numeric Catalog with Bit-Exact Conformance Vectors:
A Vendor-Neutral Reference for FP8, BF16, MXFP4, and Microscaling Formats.

## Author

**Dmitrii Vasilev**
Trinity S^3 AI
ORCID: [0009-0008-4294-6159](https://orcid.org/0009-0008-4294-6159)
Email: admin@t27.ai
GitHub: [@gHashTag](https://github.com/gHashTag)

## Repository layout

| File | Description |
|---|---|
| `main.tex` | LaTeX source of the manuscript (1094 lines, 16 pages). |
| `paper3-methodology-2026-06-08-v3-trinity.pdf` | Compiled PDF v3-trinity, 16 pp, 134 KB. SHA-256: `f31f5dd243afc7b2ba4a423859a1e1dc67036c3a93affab30acc8d02f0a15eef`. |
| `ARXIV_METADATA.md` | Submission metadata block (title, authors, categories, abstract). |
| `LICENSE` | Dual license: text under CC BY 4.0; code/metadata under MIT. |

## Abstract (excerpt)

This report documents the methodology used to construct a 84-format
numeric catalog (`FORMAT-SPEC-001.json`) with bit-exact conformance
vectors for six active formats: GF16, MXFP4 element, BF16, FP8 E4M3,
FP8 E5M2, and E8M0 block scale. Vectors are cross-validated against
`ml_dtypes 0.5.4` (Google / JAX) and ship with honest `abs_error`
columns -- non-representable inputs are not hidden as exact matches.
A documented divergence on FP8 E4M3 overflow handling (saturate-to-max
versus overflow-to-NaN, OCP MX v1.0 permits both) is published as a
Discussion section rather than smoothed over.

## Anchor

`phi^2 + 1/phi^2 = 3` (Lucas number L_2). Used as a universal numeric
check point: 3.0 is exactly representable in nearly every binary and
microscaling format in the catalog.

## Companion artefacts

- [arXiv:2606.05017](https://arxiv.org/abs/2606.05017) -- GoldenFloat
  preprint (cs.AR), anchor citation.
- [`gHashTag/t27`](https://github.com/gHashTag/t27) -- 80-format
  SSOT catalog (`specs/numeric/formats_catalog.t27`).
- [`gHashTag/tt-lang-t27`](https://github.com/gHashTag/tt-lang-t27) --
  Python package mirror (PyPI: `tt-lang-t27`), `v0.4.0` release with
  6 conformance packs.
- [`gHashTag/tt-trinity-corona`](https://github.com/gHashTag/tt-trinity-corona) --
  silicon-grade format-conformance oracle (TTGF26a / GF180MCU).
- [`gHashTag/claim-audit-lab`](https://github.com/gHashTag/claim-audit-lab) --
  public methodology audit cases.

## Citation

When the paper is on arXiv, a BibTeX entry will be added here. Until
then, please cite by the file SHA-256 above plus the repository URL.

## Reproducibility

Build environment: `tectonic 0.15.0+`, LaTeX class `article`,
`fontspec`-free pdfLaTeX-compatible pipeline. Build command:

```
tectonic -X compile main.tex
```

No external data dependencies; tables are inline literals.

## Hard rules applied

- ASCII-only manuscript body (Greek letters spelled out: `phi`, `mu`).
- No hype vocabulary (no `breakthrough`, `revolutionary`, etc.).
- Honest `abs_error` on every conformance vector that is not
  representable -- no silent zeros.
- Claim-status discipline: `[Verified]`, `[Empirical fit]`,
  `[Open conjecture]` labels where relevant.

## Status

| Date | Event |
|---|---|
| 2026-06-08 | v3-trinity finalized, ORCID locked, repo published. |
| TBD | arXiv submission (cs.AR primary, cs.MS cross-list). |

