# UC Chile Beamer Theme

A clean, UC‑Chile–flavored Beamer theme for talks and classes. Includes a minimal example, opinionated defaults, and color palette aligned with UC branding.

> **Licensing (TL;DR)**  
> - **Code (theme files)**: **Apache-2.0**  
> - **Examples/docs (text & images)**: **CC BY 4.0**  
> - **Trademarks**: UC logos/wordmarks.

---

## Features

- UC-Chile color palette for slides, accents, and emphasis.
- Sensible defaults for title page, section pages, and footers.
- Typographic tweaks for math/theorems, blocks, and lists.
- Minimal Working Example (MWE) and a build script with `latexmk`.

---

## Repository layout

```
.
├─ tex/                       # Theme code (LaTeX)
│  ├─ beamerthemeUCChile.sty
│  ├─ beamercolorthemeUCChile.sty
│  ├─ beamerfontthemeUCChile.sty
│  ├─ beamerouterthemeUCChile.sty
│  └─ beamerinnerthemeUCChile.sty
├─ examples/                  # Example slides and assets
│  ├─ example.tex             # MWE you can copy
│  └─ example.pdf             # Rendered example (screenshot-ready)
├─ rax_beamerpack.sty         # macros
├─ LICENSE                    # Apache-2.0 (theme code)
└─ README.md                  # This file
```

> If your paths differ, adjust accordingly—this is the suggested structure for clarity.

---

## Quick start

### 1) Use locally (drop-in)
Copy the `tex/*.sty` files next to your talk:

```tex
% main.tex
\documentclass[aspectratio=169]{beamer}
\usepackage{./tex/beamerthemeUCChile} % or \usetheme{UCChile} if you install in TEXMF
\title{Your Talk Title}
\subtitle{Optional subtitle}
\author{Your Name}
\institute{Institute of Mathematical Engineering and Computation\\Department of Industrial and Systems Engineering\\PUC Chile}
\date{\today}

\begin{document}
  \begin{frame}
    \titlepage
  \end{frame}

  \begin{frame}{Outline}
    \tableofcontents
  \end{frame}

  \section{Section 1}
  \begin{frame}{Theorems and Proofs}
    \begin{theorem}A nice statement.\end{theorem}
    \begin{proof}Sketch of proof.\end{proof}
  \end{frame}
\end{document}
```

Build:

```bash
latexmk -pdf main.tex
# or: pdflatex main && bibtex main && pdflatex main && pdflatex main
```

### 2) Install in your TEXMF tree
Place `*.sty` in `~/texmf/tex/latex/ucchile-beamer/` and then:

```tex
\documentclass{beamer}
\usetheme{UCChile} % if your theme registers this name
```

---

## Theme options (if you want toggles)

The theme works out-of-the-box. If you prefer switches, you can expose options like:
- `light` / `dark` — background/contrast choice  
- `progressbar=frametitle|foot` — progress indicator style  
- `titlepage=split|centered` — title slide layout  

> If you add options, document them here with short examples:
```tex
\usetheme[dark,progressbar=frametitle,titlepage=split]{UCChile}
```

---

## Color palette

The palette follows UC Chile tones (hex values reproduced from public brand references). Define them in `beamercolorthemeUCChile.sty` and reference via Beamer color hooks.

---

## Examples & screenshots

- See `examples/example.tex` for a minimal talk.  
- Use `examples/example.pdf` as a visual reference for sections, blocks, lists, and references.  
- Screenshots for your repo/README can be exported from that PDF.

---

## Branding & trademarks
- You may use `assets/titlepage-placeholder.pdf` or your own images.  
- Using this theme **does not** imply endorsement by UC Chile.  
- Follow your institution’s brand guidelines if you add official assets.

---

## License
- **Theme code (`tex/*.sty`, build scripts):** [Apache License 2.0](LICENSE)  
- Permissive reuse; includes an explicit patent grant and a NOTICE mechanism.

---

## Citation

If this theme helped your work, please cite the repository (example using generic fields):

```bibtex
@software{ucchile_beamer_theme,
  author  = {Carrasco, Rodrigo A.},
  title   = {UC Chile Beamer Theme},
  year    = {2025},
  url     = {https://github.com/drRax/UCChile-Beamer-Template,
  version = {v1.0.0}
}
```
---

## Contributing

Pull requests are welcome! Please:

1. Keep defaults minimal and consistent with Beamer conventions.  
2. Add/update example slides when you change visual behavior.  
3. Document new options in this README.  
4. Run `latexmk -pdf examples/example.tex` to verify before submitting.

---

## Acknowledgments
- Built on [`beamer`](https://ctan.org/pkg/beamer) and the LaTeX stack.  
- Thanks to students and colleagues who provided feedback on readability and contrast.
