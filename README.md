# One-file LaTeX CV template

A clean, 2-page, ATS-friendly CV written in LaTeX. Everything lives in a single
file, [`cv_template.tex`](cv_template.tex), with comments on almost every line.
[`cv_template.pdf`](cv_template.pdf) shows what it looks like.

All names, companies, numbers and links in it are placeholders. Replace them
with your own.

## 1. Turn it into a PDF

**Option A: Overleaf (nothing to install)**
1. Go to overleaf.com and sign in.
2. New Project → Upload Project → choose `cv_template.tex`.
3. Click **Recompile**. The compiler must be **pdfLaTeX** (Menu → Settings),
   which is the default.

**Option B: on your own computer**
Install a LaTeX distribution (MacTeX on macOS, TeX Live on Linux, MiKTeX on
Windows), open a terminal in this folder and run:

```bash
latexmk -pdf cv_template.tex
```

No `latexmk`? Run `pdflatex cv_template.tex` instead.

To delete the helper files LaTeX creates (`.aux`, `.log`, `.fls`, …):

```bash
latexmk -c
```

## 2. Edit it

Open `cv_template.tex`. It has two parts:

| Part | Where | What to do |
|---|---|---|
| **A: Settings** | top of the file, up to `\begin{document}` | Leave alone, or tweak the commented numbers (margins, font size, spacing). |
| **B: Your content** | from `\begin{document}` to the end | Replace the placeholder text with yours. |

Each section in Part B starts with a short "recipe" comment that you can copy to
add another job, project or bullet.

## 3. Five rules that prevent most errors

1. `%` starts a comment, so nothing after it on that line is printed.
2. Every `{` needs a matching `}`.
3. Every `\begin{...}` needs a matching `\end{...}`.
4. Put a backslash before special characters: `\%  \&  \$  \_  \#`.
5. A blank line starts a new paragraph. Single line breaks don't matter.

When the compile fails, go to the **line number** in the first error message
and look there and just above it.

## 4. Common tweaks

| I want to… | Change |
|---|---|
| Use A4 paper | `letterpaper` → `a4paper` in `\documentclass` |
| Use bigger text | `10pt` → `11pt` in `\documentclass` |
| Fit more on a page | lower `top`/`bottom`/`left`/`right` in the `geometry` block |
| Show dates on one line | increase `4.5 cm` in the `twocolentry` definition |
| Use blue links | `primaryColor` → `{RGB}{0, 79, 144}` |
| Remove a section | delete it, from its `\section{...}` to the next one |
