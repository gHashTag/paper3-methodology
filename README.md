# paper3-methodology

Golden Ruler: A Numeric Format Catalog with Bit-Exact Conformance Vectors
for FP8, BF16, MXFP4, and Microscaling Formats --
[arXiv:2606.09686](https://arxiv.org/abs/2606.09686) (v3, announced 7 Sep 2026).

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

> Note (2026-09-05): the format count is a live SSOT invariant, not a
> fixed number -- 84 in this repository's manuscript revision, 83 at
> arXiv v2 (22 Jun 2026), 109 at arXiv v3 (Sep 2026). Source of truth:
> `tools/gen_formats_catalog.py` in `gHashTag/t27` ("parsed N formats").

## Anchor

`phi^2 + 1/phi^2 = 3` (Lucas number L_2). Used as a universal numeric
check point: 3.0 is exactly representable in nearly every binary and
microscaling format in the catalog.

## Companion artefacts

- [arXiv:2606.05017](https://arxiv.org/abs/2606.05017) -- GoldenFloat
  preprint (cs.AR), anchor citation.
- [`gHashTag/t27`](https://github.com/gHashTag/t27) -- the SSOT
  catalog (`specs/numeric/formats_catalog.t27`); the format count is a
  live invariant, 109 formats as of Sep 2026.
- [`gHashTag/tt-lang-t27`](https://github.com/gHashTag/tt-lang-t27) --
  Python package mirror (PyPI: `tt-lang-t27`), `v0.4.0` release with
  6 conformance packs.
- [`gHashTag/tt-trinity-corona`](https://github.com/gHashTag/tt-trinity-corona) --
  format-conformance oracle design targeting TTGF26a / GF180MCU
  (GDS + precheck passed; not submitted, no die).
- [`gHashTag/claim-audit-lab`](https://github.com/gHashTag/claim-audit-lab) --
  public methodology audit cases.

## Citation

The paper is on arXiv as [arXiv:2606.09686](https://arxiv.org/abs/2606.09686)
(v1 8 Jun 2026; v2 22 Jun 2026, live; v3 submitted 4 Sep 2026 under the
title *Golden Ruler ...*, announced 7 Sep 2026). Cite:

> Vasilev, D. (2026). Golden Ruler: A Numeric Format Catalog with
> Bit-Exact Conformance Vectors for FP8, BF16, MXFP4, and Microscaling
> Formats. arXiv:2606.09686.

To cite this repository's manuscript revision specifically, use the
file SHA-256 above plus the repository URL.

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
| 2026-06-08 | arXiv v1 posted -- [arXiv:2606.09686](https://arxiv.org/abs/2606.09686) (cs.AR primary; cs.AI, cs.MS, cs.PF, math.NA cross-lists). |
| 2026-06-22 | arXiv v2 (17 pp), the live version. |
| 2026-09-04 | arXiv v3 submitted under the title *Golden Ruler: A Numeric Format Catalog with Bit-Exact Conformance Vectors for FP8, BF16, MXFP4, and Microscaling Formats* (19 pp; 109 formats); announces 2026-09-07. |

