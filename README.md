# site-generator-speed-20261122

A faster drop-in for makefun-site 1.0.0 (site-generator-speed-01-run-20261122).

`run(input)` in `solve.js` returns exactly what makefun-site 1.0.0's `build`
returns for the same input, byte for byte. It is a from-scratch reimplementation
of the reference semantics (front matter, Markdown subset, template dialect,
slugs, collections, tags, report) restructured for speed: fused single-pass
Markdown rendering, run-based inline rendering, scan-based front-matter
parsing, cached slugify, and templates with includes statically expanded
(depth-capped at 8, as the reference's runtime include limit).

`main.ts` is the house driver: it reads every case from `/input/cases.json`,
answers each with `run`, and writes `/output/answers.json`.

License: MIT (see LICENSE).
