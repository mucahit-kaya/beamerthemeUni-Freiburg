# Freibeamer — Unofficial Beamer Theme for the University of Freiburg

A clean, modern [Beamer](https://ctan.org/pkg/beamer) presentation theme based on the visual identity of the [University of Freiburg](https://uni-freiburg.de/). Designed for academic talks, seminar presentations, and lecture slides.

![Theme Preview](preview.png)

## Features

- Title page with university logo
- Section and subsection divider slides
- Custom footer with logo, section title, and page number
- University of Freiburg color palette (`freiBlue`)
- Clean itemize/enumerate styling
- Numbered captions with centered formatting
- 16:9 aspect ratio (configurable)
- BibLaTeX support (Biber backend, IEEE style)

## Quick Start

1. **Clone the repository:**

   ```bash
   git clone https://github.com/mucahit-kaya/beamerthemeUni-Freiburg
   cd freibeamer
   ```

2. **Edit `main.tex`** — update the title, subtitle, author, and institute fields.

3. **Add your content** in the `sections/` folder.

4. **Compile:**

```bash
pdflatex main.tex
biber main
pdflatex main.tex
pdflatex main.tex
```

Or simply with `latexmk` (handles everything automatically):

```bash
latexmk -pdf main.tex
```

**TeXShop (macOS):**
Change the compiler dropdown (top-left) from `LaTeX` to `pdflatexmk`. This runs the full `pdflatex → biber → pdflatex` chain automatically. Then compile with `Cmd + T` as usual.

**Overleaf:**
No extra configuration needed — Overleaf runs `latexmk` by default.

> **Note:** If references show as `[?]` or the bibliography is missing, it usually means `biber` has not been run.

## Project Structure

```
.
├── freibeamer/                 # Theme files and university logos
│   ├── beamerthemefrei.sty           # Main theme loader
│   ├── beamercolorthemefrei.sty      # Color definitions
│   ├── beamerinnerthemefrei.sty      # Inner theme (itemize, TOC)
│   ├── beamerouterthemefrei.sty      # Outer theme (title, footer, frametitle)
│   └── ufr_*.png / ufr_*.jpg        # University logos
├── img/                        # Images used in slides
├── sections/                   # Slide content (one file per section)
│   ├── introduction.tex
│   ├── experiment.tex
│   ├── results.tex
│   └── end.tex
├── main.tex                    # Main document
├── preamble.tex                # Package imports and theme setup
├── refs.bib                    # BibLaTeX references
└── README.md
```

## Customization

### Title Page

In `main.tex`, set:

```latex
\title{Your Title}
\subtitle{Your Subtitle}
\author{Your Name}
\date{\today}
\institute{Your Institute}
\lfooter{Left footer text}
\mfooter{Middle footer text}
```

### Colors

Edit `freibeamer/beamercolorthemefrei.sty` to change the main color:

```latex
\definecolor{freiBlue}{RGB}{45, 75, 159}
```

### Adding Sections

Create a new `.tex` file in `sections/` and include it in `main.tex`:

```latex
\input{sections/your_new_section}
```

Each section file should follow this pattern:

```latex
\section{Section Title}
\label{sec:yoursection}
\frame[plain]{\sectionpage}

\begin{frame}{Frame Title}
    % Your content here
\end{frame}
```

## Requirements

- A LaTeX distribution with Beamer support ([TeX Live](https://tug.org/texlive/), [MiKTeX](https://miktex.org/), or [MacTeX](https://tug.org/mactex/))
- `biber` for bibliography processing
- Packages: `biblatex`, `csquotes`, `booktabs`, `tabularx`, `graphicx`, `caption`, `subcaption`, `tikz`, `amsmath`, `amssymb`

## License

This project is licensed under the [MIT License](LICENSE).

> **Note:** The University of Freiburg logos included in this template are property of the University of Freiburg and are subject to their [corporate design guidelines](https://cd.uni-freiburg.de/). Use of these logos may be restricted to members and affiliates of the university.

## Acknowledgments

Inspired by the official University of Freiburg corporate design. Built with the [Beamer](https://ctan.org/pkg/beamer) LaTeX document class.

---

*Contributions, issues, and feature requests are welcome!*
