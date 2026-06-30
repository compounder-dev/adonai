# Adonai

## Stack
Rust. Standalone product — not a feature of Inference Exchange.

## Verify
`cargo fmt --check && cargo test && cargo clippy --workspace --all-targets -- -D warnings` before every commit.

## Safety
No `unsafe`, `unwrap`, or `expect` in production paths.
Local endpoints bind to loopback by default. LAN exposure requires explicit config.

## Engines
Inference engines (vLLM, MLX, llama.cpp) live behind adapters with capability detection, health checks, logs, and provenance.
If an engine, signing path, update path, or OS integration is not implemented, represent it as unavailable — never fake runtime state, benchmarks, or marketplace eligibility.
