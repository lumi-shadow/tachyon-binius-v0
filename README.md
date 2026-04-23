# Tachyon · Binius v0

A pinned, standalone copy of the **classic Binius (a.k.a. "Binius v0")** Rust workspace,
maintained as the circuit-construction *cryptographic frontend* (the M3 arithmetization DSL
and prover glue) for the Tachyon GPU prover stack.

> "Frontend" here is in the cryptographer's sense — the Rust library that turns a circuit
> description into an M3 `ConstraintSystem`. The user-facing visual node editor lives in a
> separate repository, [`lumi-shadow/Tachyon-Frontend`](https://github.com/lumi-shadow/Tachyon-Frontend).

The upstream project ([`IrreducibleOSS/binius`](https://github.com/IrreducibleOSS/binius))
was archived on 2025-09-09 in favor of [Binius64](https://docs.binius.xyz/binius_frontend/),
a different constraint system (64-bit AND/MUL words). Tachyon's GPU kernels target the
*classic* tower-field design (additive NTT, sumcheck over `F_{2^128}`, FRI over the binary
tower), so we keep this snapshot under our own control rather than depending on an archived
upstream that may move or disappear.

## Provenance

- **Upstream:** https://github.com/IrreducibleOSS/binius
- **Imported commit:** `47675e19c86c0fb676f75437073a77af8e337938`
- **Imported on:** 2026-04-23
- **Upstream license:** Apache-2.0 (preserved verbatim in [`LICENSE.txt`](LICENSE.txt))
- **Original README:** preserved at [`README.upstream.md`](README.upstream.md)

See [`ATTRIBUTION.md`](ATTRIBUTION.md) for the full attribution and modification notice
required by the Apache License, Version 2.0.

## What's in here

The full classic Binius workspace, unmodified, with these crates:

| Crate | Role |
|---|---|
| `binius_m3` | M3 arithmetization frontend — `TableBuilder`, columns, gadgets, lookups |
| `binius_core` | Constraint system, channels, prover/verifier glue, PIOP wiring |
| `binius_field` | Tower fields (`BinaryField128b` and the subfield ladder) |
| `binius_ntt` | Additive NTT |
| `binius_math` | Multilinear / univariate polynomial machinery |
| `binius_hash` | In-protocol hashes (Vision, Groestl, Keccak adapters) |
| `binius_compute`, `binius_fast_compute`, `binius_hal` | Compute backends and HAL |
| `binius_macros`, `binius_utils`, `binius_maybe_rayon` | Support crates |

Plus `examples/`, `doc/`, `scripts/`, `testgen/`.

## Why "Tachyon Frontend" and not "binius v0"?

The **project** is renamed for clarity inside the Tachyon stack. The **library names**
are unchanged — your downstream code still imports `binius_m3`, `binius_core`, etc.
The "Binius" name and any associated trademarks remain the property of Irreducible Inc.;
we make no claim to them, and the rename of this repository is not intended to imply
endorsement by Irreducible Inc.

## Using as a git dependency

```toml
[dependencies]
binius_m3 = { git = "https://github.com/lumi-shadow/Tachyon-Frontend", rev = "<pin a sha>" }
binius_core = { git = "https://github.com/lumi-shadow/Tachyon-Frontend", rev = "<pin a sha>" }
binius_field = { git = "https://github.com/lumi-shadow/Tachyon-Frontend", rev = "<pin a sha>" }
```

Always pin to a specific `rev` so reproducibility doesn't drift.

## Building

Standard cargo workflow:

```bash
cargo build --workspace
cargo test  --workspace
```

A `rust-toolchain.toml` is included; `rustup` will pick the right channel automatically.

## License

Apache License, Version 2.0 — see [`LICENSE.txt`](LICENSE.txt).

This repository is a derivative work of `IrreducibleOSS/binius`. All original files retain
their `// Copyright YYYY Irreducible Inc.` headers. Modifications made when packaging this
snapshot are documented in [`ATTRIBUTION.md`](ATTRIBUTION.md), as required by §4(b) of the
Apache License, Version 2.0.
