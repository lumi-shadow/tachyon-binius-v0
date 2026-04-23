# Attribution and Modification Notice

This repository is a derivative work governed by the Apache License, Version 2.0.

## Source

- **Upstream project:** `IrreducibleOSS/binius` ("Binius v0", classic tower-field Binius)
- **Upstream URL:** https://github.com/IrreducibleOSS/binius
- **Upstream commit:** `47675e19c86c0fb676f75437073a77af8e337938`
- **Upstream commit subject:** *Binius is dead, long live Binius (#833)*
- **Upstream commit date:** 2025-09-09
- **Upstream license:** Apache License, Version 2.0
- **Upstream copyright holder:** Irreducible Inc.

## What this repository is

A repackaging of the upstream workspace as **Tachyon Frontend**, intended for use as the
circuit-construction frontend for the Tachyon GPU prover. The upstream repository was
archived by its maintainers in favor of [Binius64](https://docs.binius.xyz/binius_frontend/),
which is a different (incompatible) constraint system; Tachyon depends on the classic
design that this snapshot preserves.

## Modifications made on import (2026-04-23)

In compliance with §4(b) of the Apache License, Version 2.0, the following changes were
made when importing the upstream tree into this repository:

1. The git history of the upstream repository was **not** preserved. This repository
   begins with a single import commit. The upstream project remains accessible at
   https://github.com/IrreducibleOSS/binius for full revision history.
2. The upstream `README.md` was **renamed** to `README.upstream.md` and preserved verbatim.
3. A new top-level `README.md` was added describing this repository's purpose and pointing
   back to the upstream project.
4. This `ATTRIBUTION.md` file was added.

**No source files (`.rs`, `Cargo.toml`, build scripts, examples, docs, etc.) have been
modified.** All `// Copyright YYYY Irreducible Inc.` headers in source files are preserved
exactly as they appear upstream. The Apache-2.0 `LICENSE.txt` is preserved verbatim.

If and when this repository diverges from upstream — for example to add Tachyon-specific
patches, a slim crate subset, or GPU-backend integration shims — those changes will be
recorded in this file with the date, the affected files, and a short description of the
change, alongside the standard "modified by Tachyon contributors, YYYY" notice in any
file actually edited.

## Trademark

"Binius" and any associated marks are the property of Irreducible Inc. The Apache License,
Version 2.0 grants no rights to use such trademarks (§6). The renaming of this repository
to "Tachyon Frontend" is not intended to imply any endorsement, sponsorship, or
affiliation by or with Irreducible Inc.
