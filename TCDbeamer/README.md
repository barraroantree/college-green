# College Green — Beamer Theme for Trinity College Dublin

A LaTeX Beamer presentation theme loosely based on the official Trinity College Dublin visual identity.
Inspired by [Enda Hargaden's](https://github.com/endahargaden) *Belfield* theme for UCD.

---

## Files

| File | Purpose |
|---|---|
| `beamerthemecollegegreen.sty` | The theme |
| `CollegeGreen_ThemeExample.tex` | Working example (see below to compile) |
| `refs.bib` | Example BibTeX file used by the example |
| `Trinity-Main-Logo.jpg` | Main English logo — embedded automatically on title page |
| `TCD-logo-Irish-RGB.jpg` | Irish-language logo — swap in if desired (see below) |
| `trinity-virtual-background-11.jpg` | Campus image used in the example |

---

## Quick start

```latex
\documentclass[aspectratio=169]{beamer}
\usetheme{collegegreen}
\usepackage{natbib}
\usepackage{hyperref}
\hypersetup{
  colorlinks=true,
  linkcolor=TrinityBlue,
  urlcolor=pms_512,
  citecolor=pms_512,
}

\title{Your Title}
\subtitle{Your Subtitle}
\author{Your Name}
\institute{Trinity College Dublin, the University of Dublin}
\date{Hilary Term 2025/26}

\begin{document}
\begin{frame}\titlepage\end{frame}
% ... your slides ...
\end{document}
```

Place `beamerthemecollegegreen.sty` and `Trinity-Main-Logo.pdf` in the same directory as
your `.tex` file, or install them on your LaTeX path (e.g. `~/texmf/tex/latex/collegegreen/`).

---

## Compiling

Without references:
```bash
pdflatex main.tex
```

With natbib references:
```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

---

## Colour palette

### Primary

| Macro | PMS | HEX | Role |
|---|---|---|---|
| `pms_300` / `TrinityBlue` | 300 | `#0569b9` | Titles, structure, footer, internal links |
| `pms_coolgrey` / `CoolGrey` | Cool Grey 11 | `#50555a` | Subtitles, subitem bullets |
| `pms_black` / `pms_white` | Black / White | `#000000` / `#ffffff` | |

### Secondary

| Macro | PMS | HEX |
|---|---|---|
| `pms_312` | 312 | `#00aacd` |
| `pms_326` | 326 | `#00b4aa` |
| `pms_360` | 360 | `#32d732` |
| `pms_375` | 375 | `#96d700` |
| `pms_389` | 389 | `#d2e100` |
| `pms_109` | 109 | `#ffd200` |
| `pms_466` | 466 | `#c8aa78` |
| `pms_165` | 165 | `#ff641e` |
| `pms_485` | 485 | `#dc281e` |
| `pms_512` | 512 | `#823278` — citations, URLs, `\href` links |
| `pms_280` | 280 | `#001e69` |
| `pms_gold` | Gold 871 | `#85754e` — metallic approx. |
| `pms_silver` | Silver 877 | `#8a8d8f` — metallic approx. |

Each colour also has `_75`, `_50`, `_25`, and `_10` tint variants,
e.g. `pms_312_50`. Source: [TCD Visual Identity Handbook](https://www.tcd.ie/identity/colour-palette/).

---

## Features

- **Title page** — logo embedded automatically on a white canvas
- **Footer** — TrinityBlue bar showing "*Trinity College Dublin*, the University of Dublin" and frame number; hidden on standout slides
- **Font** — Source Sans Pro (Trinity's recommended sans-serif face) loaded automatically
- **Hyperlinks** — `\href` and `\url` use `pms_512`; internal links use `TrinityBlue`; natbib `\citet`/`\citep` citation links use `pms_512` with parentheses kept in body text colour
- **Blocks** — rounded, shadowed blocks with TrinityBlue header bar
- **Standout frames** — full-bleed TrinityBlue slide with white text
- **Margins** — 0.25 in left/right

---

## Title page logo

The theme defaults to `Trinity-Main-Logo.pdf` (English). To use the Irish-language logo instead, override the title page template in your preamble:

```latex
\setbeamertemplate{title page}{%
  \begin{center}
    \vspace{0.5\baselineskip}
    \includegraphics[width=0.45\textwidth]{TCD-logo-Irish-RGB}
    % ... rest of title page content ...
  \end{center}
}
```

Or simply swap the file — rename `TCD-logo-Irish-RGB.jpg` to `Trinity-Main-Logo` and the theme will pick it up automatically.

---

## Standout slides

```latex
\begin{frame}[standout]
  Section break or key takeaway
\end{frame}
```

---

## Acknowledgements

Structure and standout-frame code adapted from Enda Hargaden's
[*Belfield* theme](https://github.com/endahargaden) (UCD, 2023), which is itself
based on the [Metropolis](https://github.com/matze/mtheme) Beamer theme.