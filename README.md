# AllReader

PDF reader and editor for All.Q Agencia: a native Rust desktop app, local and private, with no telemetry,
no account and no cloud processing. Internal tool, not sold or distributed.

AllReader is built on [PdfCraft](https://github.com/storytold/pdfcraft), an open-source, clean-room PDF
application licensed `MIT OR Apache-2.0`. The ArtCraft name and logos were removed from this fork, as the
terms of those marks require. The crates, binaries and packaging keep the original `pdfcraft` names
internally, so the build and the installer need no change; only what people see is AllReader.

## Run

```sh
cargo run -p pdfcraft -- file.pdf        # the desktop app
cargo run -p pdfcraft-cli -- tools       # the headless automation tools
```

Rust 1.90 or newer and a C compiler are required.

## Check

```sh
cargo xtask assets                       # every asset needs an entry in ATTRIBUTION.toml
cargo fmt --check
cargo clippy --workspace -- -D warnings
cargo test --workspace
```

## Where things are

| Path | What |
|---|---|
| `AGENTS.md`, `CLAUDE.md` | Rules for agents working on the code: asset policy, clean-room rules, never-crash rules |
| `assets/app-icon/` | The app icon and the PDF file icon (pixel art), see its README |
| `assets/brand/` | The horizontal AllReader logos and the brand notes |
| `ATTRIBUTION.toml` | Every asset with author, source, licence and SHA-256 (`ATTRIBUTION.md` is generated) |
| `docs/`, `ROADMAP.md`, `parity/` | Design notes, roadmap and the feature checklist inherited from PdfCraft |

## Licence

`MIT OR Apache-2.0` (LICENSE-MIT, LICENSE-APACHE). Copyright (c) 2026 ArtCraft Team and the PdfCraft
contributors; the AllReader icons and logos are Copyright (c) 2026 All.Q Agencia. Required notices are in
[NOTICE](NOTICE).
