# AllReader app icon

<img src="pdfcraft-small.svg" alt="AllReader app icon: a white page with a gold folded corner on red" width="128">

Pixel art in the All.Q style: a 16 by 16 grid of square modules (module 16, visible 15, gap 1 on a 256 canvas).
Approved by the owner on 2026-10-31. Brand notes and the horizontal logos are in [`../brand/`](../brand/README.md).

**Palette:** red `#C0261B` (field and banner), white (page), Honey `#F0AD0C` (folded corner), Jet `#2F2F2F` (document
icon outline). Red is a deliberate exception to the All.Q palette, chosen by the owner.

**Provenance:** original work by Kassio Braga for All.Q Agencia, drawn as rectangles and rendered to PNG, ICO and
ICNS by a pixel rasterizer (no antialiasing, so modules stay crisp). Licence: [LICENSE.txt](LICENSE.txt)
(`MIT OR Apache-2.0`, like the repo). The Adobe Acrobat icon was not used or traced.

The file names keep the old internal name `pdfcraft` so the build, packaging and installer need no change.

## Files

| File | What it is |
|---|---|
| `pdfcraft.svg` | the master vector of the app icon |
| `pdfcraft-small.svg` | same drawing, used in this README |
| `pdfcraft-1024.png` | 1024 px on Apple's grid (824 px body on a transparent canvas); also the runtime Dock icon on macOS |
| `pdfcraft.icns` | macOS icon (16-1024 px) |
| `pdfcraft.ico` | Windows icon (16-256 px), embedded in `pdfcraft.exe` by `apps/pdfcraft/build.rs` |
| `pdfcraft-document.svg` | Windows PDF file icon master: white page, gold fold, red banner with PDF lettering, Jet outline |
| `pdfcraft-document.ico` | Windows PDF file icon (16-256 px), embedded as resource 2 in `pdfcraft.exe` |
| `hicolor/<n>x<n>/apps/ai.storyteller.pdfcraft.png` | Linux hicolor theme, 16-512 px; the 256 px one is the runtime icon on Windows and Linux |
| `hicolor/scalable/apps/ai.storyteller.pdfcraft.svg` | Linux scalable icon (copy of the master) |

Where it shows: `apps/pdfcraft/src/main.rs` sets the window icon (Dock, taskbar, Alt-Tab, launcher) and the
Wayland app id `ai.storyteller.pdfcraft`; `packaging/linux/ai.storyteller.pdfcraft.desktop` names the hicolor icon.
Windows PDF files use resource 2 (`"pdfcraft.exe",-2`) when AllReader is chosen as the default reader; the app
keeps resource 1.

## Regenerate

The PNG, ICO and ICNS files were produced from the two master SVGs with a small pixel rasterizer that samples each
module exactly. `packaging/icons.sh` (resvg) still works but antialiases the 1 px gaps at small sizes, so the icons
come out softer. After any change, update the `sha256` values in `ATTRIBUTION.toml` and run
`cargo xtask assets --write`.
