---
title: "LaTeX-Integration in VS Code"
excerpt_separator: "<!--more-->"
categories:
  - Blog
tags:
  - Latex
  - deutsch
  - Tools
---

In diesem Beitrag wird kurz beschrieben, wie VS Code für die LaTeX Kompilierung genutzt und konfiguriert werden kann.
<!--more-->

# Installation & Konfiguration
- [MacTex](https://tug.org/mactex/downloading.html) herunterladen und installieren.
- Die VS Code Extension latex-workshop installieren.
- In View >> Command Palette >> User settings folgendes einfügen:

```
      "latex-workshop.latex.tools": [
        {
        "name": "xelatex",
        "command": "xelatex",
        "args": [
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "%DOC%"
        ]
        }
        ],
        "latex-workshop.latex.recipes": [
        {
        "name": "xelatex",
        "tools": [
        "xelatex"
        ]
        }
        ],
        "latex-workshop.latex.build.forceRecipeUsage": true,
        "latex-workshop.view.pdf.invert": 0.8
```
Hier kann der LaTeX-Compiler eingestellt werden, sowie durch `latex-workshop.view.pdf.invert` den DarkMode für den Pdf-Betrachter einstellen. 
