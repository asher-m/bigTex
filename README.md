# BigTeX
A multi-file LaTeX project template

This project exists because I'm tired of getting stuck in
multiple-tens-of-thousands-of-line Overleaf projects where no one has broken
the primary source document into its respective sections, etc...

Working in such large files is exhausting.

I'm hoping, by having set this up once, I can reuse the directory structure of
this document to simplify the writing process for other documents on which I work.

## Layout

- `main.tex` defines the document order and includes each chapter with `\subfile`.
- `chapters/*.tex` are independently compilable chapters. Use `\subfile` in the
  main build to keep that workflow; a master build still typesets every chapter.
- `packages.tex` contains document-wide packages and `config.tex` contains
  document settings and metadata. Both are included with `\input`.
- `bigtex-macros.sty` contains reusable macros. Put project- or domain-specific
  commands in `document-macros.tex`.
- `figures/` holds images organized by chapter.

## Getting Started

Clone this repository, then build `main.tex`, e.g., `latexmk -pdf main.tex`.

To work on one chapter, use `latexmk -cd -pdf chapters/intro.tex`; `-cd` makes
the chapter directory the working directory, which is required by its
`../main.tex` subfile preamble reference.  Alternatively, VS Code's LaTeX Workshop
handles working directly configuration automatically, so it should work
out-of-the-box.
