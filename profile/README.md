<p align="center">
  <img src="media/banner.png" alt="Quire — lossless DOCX typescraft" width="860"/>
</p>

# Quire Office

**Lossless Office document engines in Rust.**

Office documents are the world's most portable data format — and the least respected.
Round-trip a real-world `.docx` through most open tools and you silently lose the parts
they don't understand. We build engines where that is structurally impossible: what we
don't touch, we write back byte-for-byte.

## Products

| Project | Format | Status | What it is |
|---|---|---|---|
| **[quire](https://github.com/quire-office/quire)** | DOCX | preview | Rust typesetting engine: lossless OPC round-trip (130/130 corpus files byte-identical in CI), Knuth-Plass line breaking, incremental pagination, native + wasm from one core |

XLSX and PPTX join the family as sibling format crates on the same core — same OPC
container, same lossless guarantee, same layout machinery.

## What we optimize for

- **Lossless by construction** — untouched parts are copied byte-for-byte, verified by a CI gate on every push, not by hope.
- **One core, two shells** — the engine is one Rust codebase compiled for native and `wasm32-unknown-unknown`; shells are thin platform adapters, and the boundary is machine-enforced.
- **Cross-platform is the baseline** — the same gates run on Linux, macOS and Windows: formatting, clippy, tests, wasm link, bundle-size ceiling, round-trip.

## Where we are

DOCX parsing, lossless round-trip, line breaking (Latin + CJK), pagination and a
display-list render contract are green. Tables are in progress; headers/footers,
columns and tracked changes are next on the board. The repository is currently
private while the foundation firms up — it opens when the foundations are solid.

## About this org

Everything here is built to one standard: **a document that goes in must come out
the same document** — and a browser tab must render what a desktop renders.

<!-- website placeholder: add links to quireoffice.dev + docs here once the domain is live -->
