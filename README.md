# CldOps Cheatsheet

Dense exam cheat sheet for the Cloud Operations module — A4 landscape, 5 columns.

## Build

Compile with **LuaLaTeX** (not pdfLaTeX — `fontspec` loads the system Verdana font):

```
lualatex main.tex
```

(or `latexmk -lualatex main.tex`). The `% !TEX TS-program = lualatex` line at the top
of `main.tex` tells most editors which engine to use.

**Needs:** a TeX distro with `fontspec`, `microtype`, `titlesec`, `mdframed`,
`listings`, `enumitem`, `tikz` (MiKTeX installs these on the fly), and **Verdana**
as a system font (default on Windows). To build elsewhere, change `\setmainfont`
in `main.tex`.

## Printer settings

- Margins are **5 mm** all around (`\geometry` in `defs.tex`) — about the tightest
- **6mm** on the right because otherwise the printer cuts off some text
- Could be condensed to 4 Pages, then easy print 2 on 1 page, also easily readable on 4 on 1, but currently lots of free space
- Set OST printer to 1200 DPI

## How it's organised

- `main.tex` — preamble + the `multicols` body; `\input`s each section file.
- `defs.tex` — all styling: geometry, theme colours, title bars, `listings` setup, helper macros.
- `inhalt/*.tex` — one file per section (intro, gitlab, terraform, …).
- `media/` — images (`devops.png`, `ServiceMesh.png`).
