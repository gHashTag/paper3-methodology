# arXiv Submission Metadata — Paper #3 (Catalog Methodology)

**File:** `paper3-methodology-2026-06-08-v3-trinity.pdf`
**SHA-256:** `f31f5dd243afc7b2ba4a423859a1e1dc67036c3a93affab30acc8d02f0a15eef`
**Pages:** 16
**Bytes:** 134 KB
**Built:** 2026-06-08 14:47 +07 (tectonic)

---

## Required arXiv Submission Fields

### Title
```
An 84-Format Numeric Catalog with Bit-Exact Conformance Vectors:
A Vendor-Neutral Reference for FP8, BF16, MXFP4, and Microscaling Formats
```

### Authors (single)
```
Dmitrii Vasilev
Trinity S^3 AI
ORCID: 0009-0008-4294-6159
```

### Author email
```
admin@t27.ai
```

### Author ORCID
```
0009-0008-4294-6159
https://orcid.org/0009-0008-4294-6159
```

### Affiliation block (ASCII form, arXiv form)
```
Trinity S^3 AI
```

### Primary category
```
cs.AR  (Hardware Architecture)
```

### Cross-list categories
```
cs.MS  (Mathematical Software)
cs.PF  (Performance)  -- optional, only if room
```

### MSC classification
```
68N99  (Software, none of the above)
68W99  (Algorithms, none of the above)
```

### ACM classification
```
B.2.0  Arithmetic and Logic Structures - General
D.2.4  Software/Program Verification
```

### Comments string (free-form, shown on abstract page)
```
16 pages, 8 tables. Companion repository at
https://github.com/gHashTag/t27. Six conformance packs released under
gHashTag/t27 (v0.3.1 on PyPI, v0.4.0-pre in PR #6). Anchor identity
phi^2 + 1/phi^2 = 3 from arXiv:2606.05017.
```

### License
```
arXiv non-exclusive license to distribute (default).
Underlying artifacts (catalog, packs, codegen): Apache-2.0.
```

---

## Abstract (verbatim, copy-paste form for arXiv form)

```
Numeric format proliferation in machine learning hardware -- FP8 (E4M3 and
E5M2), BF16, MXFP4, microscaling block formats, and dozens of research
variants -- has outpaced the availability of vendor-neutral, bit-exact
reference material. Engineers porting models across accelerators encounter
silent divergences that are difficult to diagnose without a shared ruler.

This paper describes a catalog of 84 numeric formats spanning 13 families,
and a suite of six bit-exact conformance packs covering GF16, MXFP4
element, BF16, FP8 E4M3, FP8 E5M2, and E8M0 block scale. Each pack is a
self-contained JSON document with a SHA-256 fingerprint, a shared row
schema, and an anchor vector that encodes 3.0 -- the identity
phi^2 + 1/phi^2 = 3 (arXiv:2606.05017) -- as a cross-pack sanity check.
Packs are cross-validated against ml_dtypes 0.5.4 (Google/JAX); any
divergence is documented explicitly and interpreted as a spec-permitted
interpretation gap rather than hidden. The work is framed as registry
filling: it does not propose new formats, make model-accuracy claims, or
assert superiority over any vendor's implementation. All artifacts are
publicly available at https://github.com/gHashTag/t27 under an open
license.
```

(Note: arXiv abstract form requires plain ASCII; the form above uses
`phi^2` rather than the LaTeX `\varphi^{2}` rendered in the PDF.)

---

## Submission Checklist

- [x] PDF builds with tectonic from `main.tex` deterministically
- [x] SHA-256 recorded for v3 PDF
- [x] Bibliography 18 refs, all with URLs, no placeholder entries
- [x] Affiliation = `Trinity S^3 AI` (not "Independent Researcher")
- [x] Acknowledgments thank ml_dtypes maintainers + tt-metal reviewers
- [x] No DARPA/SBIR/CLARA mentions anywhere
- [x] No hype words (breakthrough/revolution/prize/etc.)
- [x] All claim-status labels honest (Verified/Efit/Conj/Risk/Retr)
- [x] Anchor SHA-256 of `phi^2 + 1/phi^2 = 3` published in section 8.3
- [x] Limitations section (section 10) explicit, 7 paragraph-blocks
- [x] §7.2 Table 7 documents MXFP4 vs NVFP4 block-structure parameters
- [x] Cross-refs all resolve (verified via tectonic log -- no LaTeX Warning: Reference)
- [x] **User ORCID = 0009-0008-4294-6159** -- locked
- [ ] **User repo-home decision (A/B/C)** -- pending
- [ ] **User submit click** -- pending

---

## Where to upload

1. `https://arxiv.org/submit` (after `https://arxiv.org/user/login`)
2. Choose Primary category `cs.AR`, cross-list `cs.MS`
3. Upload `paper3-methodology-2026-06-08-v3-trinity.pdf` OR upload source tarball:
   - `main.tex` + bibliography embedded (no external .bib needed)
   - tectonic builds deterministically from this single file
4. Paste the Abstract block above
5. Paste the Comments string above
6. Submit; arXiv assigns ID within 24-48 hours of moderation queue

---

## Source repository sync plan (not yet executed)

**Note:** `gHashTag/arith2027-goldenfloat` is the **ARITH 2027 GoldenFloat
submission scaffold** (a different paper). Paper #3 (catalog methodology)
needs a different home. Three options:

**Option A: New dedicated repo `gHashTag/paper3-methodology`** (preferred)
- Pros: clean separation of paper from code; arXiv-ready ancillary files
- Cons: one more repo to maintain
- Cost: ~5 minutes to bootstrap (LICENSE, README, .gitignore, main.tex,
  PDF, ARXIV_METADATA.md)

**Option B: Add `conformance/paper/` subdirectory to `gHashTag/t27`**
- Pros: paper lives next to the code/data it documents
- Cons: mixes manuscript with codebase; harder to tag releases independently
- Cost: ~3 minutes

**Option C: Add `paper3/` subdirectory to `gHashTag/arith2027-goldenfloat`**
- Not recommended: this repo is the ARITH 2027 conference scaffold,
  paper #3 is the open-access catalog manuscript -- different purposes

Until user picks, source remains in workspace at
`/home/user/workspace/sprint_2026-06-08/paper/main.tex`.

In parallel, `scientific-works-canon` SKILL.md has been updated to v1.6
delta with the v3 PDF SHA-256 and 16pp/134KB metrics.

---

## TECH TREE coordinates

L1 (math anchor `phi^2 + 1/phi^2 = 3`) -> L3 (84 formats catalog) -> L6
(paper #3 v3, 16pp, Trinity S^3 AI) -> L7 (arXiv #3 submit window, T-7d) ->
L8 (post-arXiv: lifts no-arXiv-yet block for non-Stream-C asks; Stream-C
still gated on Pellis paper)
