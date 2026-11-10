# PRAXO-CORE for GNU Octave

Dedicated repository for the GNU Octave implementation of PRAXO-CORE: an
embeddable, MIT-licensed agent execution kernel with policy controls,
human-in-the-loop approval, checkpoints, events, and tool calling.

- Package: `praxo-core` (Octave package)
- Documentation: https://axisvela.github.io/praxo-core/languages/octave/
- Canonical source: https://github.com/axisvela/praxo-core/tree/main/language/octave
- Release index: https://axisvela.github.io/praxo-core/languages/registry-status/

This repository is a discovery mirror of the canonical Octave source. The
monorepo remains the source of truth and the release workflow source. Shared
conformance vectors are included under `spec/`; the shared MATLAB/Octave core is
under `language/matlab-octave-core`.

Octave Packages registration PR #875 is pending. Verification under GNU Octave
does not establish MATLAB behavior.

## Install or build

Use the published Octave package archive, or build from `language/octave` with
`build_octave_package.py`.

## Verify

Build and test instructions are in `language/octave/README.md`. The monorepo CI
runs the Octave conformance and package-install smoke.

PRAXO-CORE is not a hosted model, workflow engine, identity provider, or safety
controller. Do not infer exactly-once execution, complete sandbox isolation,
production security certification, live-provider behavior, or physical safety
from this package.

MIT licensed.
