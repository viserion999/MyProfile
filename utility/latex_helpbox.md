# LaTeX – Build Instructions

Compile `.tex` to PDF using VS Code (with or without extensions).

---

## Prerequisites

Install a LaTeX distribution:

**Linux (Ubuntu/Debian):**
```bash
sudo apt update && sudo apt install texlive-latex-extra latexmk

```
Verify: `pdflatex --version`

---

## Method 1: VS Code + LaTeX Workshop *(Recommended)*

Provides live preview & auto-compilation (Overleaf-like experience).

1. Install **LaTeX Workshop** extension (`Ctrl+Shift+X`)
2. Add to settings (`Ctrl+,`):
   ```json
   { "latex-workshop.latex.autoBuild.run": "onSave" }
   ```
3. **Build:** `Ctrl+Alt+B` | **Preview:** `Ctrl+Alt+V`

---

## Method 2: Terminal Only

Minimal setup, works everywhere.

1. Open terminal: `` Ctrl+` ``
2. Run:
   ```bash
   pdflatex resume.tex
   pdflatex resume.tex
   ```

📄 PDF generated in the same folder.

**Or use `latexmk`** (auto-handles dependencies):
```bash
latexmk -pdf resume.tex   # Build
latexmk -c                # Clean aux files
```

---

## Troubleshooting

| Issue | Fix |
|-------|-----|
| `pdflatex: command not found` | Install TeX Live / MiKTeX |
| PDF not updating | Run `pdflatex` twice or use `latexmk` |