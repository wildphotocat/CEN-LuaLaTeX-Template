# Catalysis Education Newsletter - LaTeX Template

![Version](https://img.shields.io/badge/version-4.0-blue)
![License](https://img.shields.io/badge/license-CC--BY--SA--4.0-green)
![LaTeX](https://img.shields.io/badge/LaTeX-LuaLaTeX-orange)

Official LaTeX template for submitting articles to the **Catalysis Education Newsletter**.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Requirements](#requirements)
- [Quick Start](#quick-start)
- [Template Structure](#template-structure)
- [Article Types](#article-types)
- [Usage Guide](#usage-guide)
- [Special Features](#special-features)
- [Submission Guidelines](#submission-guidelines)
- [Examples](#examples)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## 🌟 Overview

The Catalysis Education Newsletter template provides a professional, journal-quality format for catalysis education articles. It features a modern two-column layout with integrated chemistry packages, colored highlight boxes, and automated formatting for authors, affiliations, and citations.

## ✨ Features

- **Professional Layout**: Two-column format with customized headers and footers
- **Chemistry Support**: Built-in support for chemical formulas (mhchem), structures (chemfig), and reactions
- **Colored Boxes**: Four types of highlight boxes (Concept, Note, Highlight, Caution)
- **Author Integration**: Automatic formatting for ORCID, Google Scholar, and LinkedIn
- **Open Access**: CC BY-NC 4.0 license badge included
- **Responsive Design**: Optimized for both print and digital distribution
- **Bibliography**: ACS-style citations with natbib
- **Hyperlinks**: Fully hyperlinked DOIs, ORCIDs, and references

## 📦 Requirements

### Required LaTeX Distribution
- **TeX Live 2020** or later
- **MiKTeX 2020** or later

### Compiler
- **LuaLaTeX** (required for font support)

### Required Packages
The template requires the following LaTeX packages (usually included in modern distributions):

```
fontspec, unicode-math, siunitx, geometry, enumitem, lineno,
tcolorbox, amsmath, amsthm, amssymb, booktabs, tabularx, ragged2e,
xcolor, mhchem (v4), chemfig, chemmacros, titlesec, needspace,
etoolbox, graphicx, wrapfig, float, caption, microtype, natbib,
hyperref, tikz, fontawesome5, fancyhdr
```

### Required Font Families
- TeX Gyre Termes (Times-like serif)
- TeX Gyre Heros (Helvetica-like sans-serif)
- TeX Gyre Cursor (monospace)
- Source Serif 4
- STIX Two Math

### Required Image Files
Place these files in the same directory as your `.tex` file:
- `logodec_updated.pdf` - Newsletter logo
- `orcid.pdf` - ORCID icon
- `ccby.pdf` - Creative Commons icon

## 🚀 Quick Start

### 1. Download the Template

```bash
git clone https://github.com/catalysis-education/latex-template.git
cd latex-template
```

### 2. Edit Metadata

Open `catalysis_education_template.tex` and fill in your information:

```latex
\malar{1}                          % Volume number
\petal{1}                          % Issue number
\yearval{2026}                     % Publication year
\articletype{Educational Article}  % Article type

\title{Your Article Title}

\author{%
  \textbf{Your Name}\textsuperscript{1\,\href{mailto:your.email@domain.edu}{\faEnvelope}} 
  \orcid{0000-0000-0000-0000}
  \href{https://scholar.google.com/...}{\small \faGraduationCap} 
  \href{https://www.linkedin.com/...}{\small \faLinkedin}
}

\affiliation{%
  \textsuperscript{1}Your Department, Your University, City, Country
}

\keywords{keyword1, keyword2, keyword3}
```

### 3. Compile with LuaLaTeX

```bash
lualatex catalysis_education_template.tex
bibtex catalysis_education_template
lualatex catalysis_education_template.tex
lualatex catalysis_education_template.tex
```

Or use your preferred LaTeX editor (Overleaf, TeXworks, TeXstudio) with LuaLaTeX selected.

## 📁 Template Structure

```
catalysis_education_template.tex    # Main template file
├── Preamble (lines 1-350)
│   ├── Package imports
│   ├── Font configuration
│   ├── Color definitions
│   ├── Custom commands
│   └── Page styles
├── Metadata Section (lines 351-400)
│   └── Fill in your article information here
└── Document Body (lines 401+)
    ├── First page (single column)
    │   ├── Title and authors
    │   ├── Abstract
    │   ├── Keywords
    │   └── Broader Context
    └── Main content (two columns)
        ├── Introduction
        ├── Your sections
        ├── Conclusion
        └── Author Information
```

## 📚 Article Types

The newsletter accepts four types of contributions:

### 1. Educational Article
Comprehensive tutorials or review articles on catalysis topics. Typically 4,000-8,000 words.

```latex
\articletype{Educational Article}
```

### 2. Concept Note
Focused explanations of specific concepts or techniques. Typically 2,000-4,000 words.

```latex
\articletype{Concept Note}
```

### 3. Paper Commentary
Critical analysis of recent important publications. Typically 1,500-3,000 words.

```latex
\articletype{Paper Commentary}
```

### 4. Teaching Material
Resources for catalysis education (problem sets, case studies, etc.). Variable length.

```latex
\articletype{Teaching Material}
```

## 📖 Usage Guide

### Chemical Formulas

Use the `mhchem` package for all chemical formulas:

```latex
\ce{H2O}           % Water
\ce{H2SO4}         % Sulfuric acid
\ce{CH3OH}         % Methanol
\ce{2H2 + O2 -> 2H2O}  % Reaction
```

### Figures

For **full-width figures** (spanning both columns):

```latex
\begin{figure*}[t]
  \centering
  \includegraphics[width=0.8\textwidth]{your_figure.pdf}
  \caption{Your descriptive caption here.}
  \label{fig:example}
\end{figure*}
```

For **single-column figures**:

```latex
\begin{figure}[h]
  \centering
  \includegraphics[width=\columnwidth]{your_figure.pdf}
  \caption{Single column figure.}
  \label{fig:single}
\end{figure}
```

### Tables

For **full-width tables**:

```latex
\begin{table*}[t]
  \centering
  \caption{Your table caption.}
  \label{tab:example}
  \begin{tabular}{lcc}
    \toprule
    Parameter & Value & Unit \\
    \midrule
    Temperature & 298 & K \\
    Pressure & 1.0 & bar \\
    \bottomrule
  \end{tabular}
\end{table*}
```

### Equations

```latex
\begin{equation}
  k = A e^{-E_a/RT}
  \label{eq:arrhenius}
\end{equation}

As shown in Equation~\ref{eq:arrhenius}, ...
```

## 🎨 Special Features

### Colored Boxes

The template provides four types of colored highlight boxes:

#### Concept Box (Green)
```latex
\begin{conceptbox}
  Fundamental concepts and theoretical background.
\end{conceptbox}
```

#### Note Box (Blue)
```latex
\begin{notebox}
  Important notes and additional information.
\end{notebox}
```

#### Highlight Box (Yellow)
```latex
\begin{highlightbox}
  Key findings and take-home messages.
\end{highlightbox}
```

#### Caution Box (Red)
```latex
\begin{cautionbox}
  Warnings, pitfalls, and safety considerations.
\end{cautionbox}
```

### ORCID Integration

The template automatically formats ORCID links:

```latex
\orcid{0000-0000-0000-0000}
```

### Social Links

Include Google Scholar and LinkedIn links:

```latex
\href{https://scholar.google.com/citations?user=XXXXX}{\small \faGraduationCap}
\href{https://www.linkedin.com/in/username}{\small \faLinkedin}
```

## 📤 Submission Guidelines

### Before Submitting

Ensure you have:

- [ ] Compiled successfully with LuaLaTeX
- [ ] Completed all metadata fields
- [ ] Provided ORCID, email, Google Scholar, and LinkedIn for all authors
- [ ] Included all required image files
- [ ] Written an abstract of 150-250 words
- [ ] Provided 5-8 relevant keywords
- [ ] Formatted all chemical formulas using `\ce{}`
- [ ] Numbered and referenced all equations, figures, and tables
- [ ] Prepared bibliography in BibTeX format
- [ ] Checked for compilation errors
- [ ] Added AI disclosure if applicable

### Submission Package

Submit the following files:

1. `.tex` file (your manuscript)
2. `.bib` file (bibliography)
3. All figure files (PDF, PNG, or JPG)
4. Required icon files (`orcid.pdf`, `ccby.pdf`, `logodec_updated.pdf`)

### Where to Submit

Email your complete package to: **catalysiseducation@gmail.com**

## 💡 Examples

### Example Article Structure

```latex
\section{Introduction}
Background and motivation for your article.

\section{Fundamental Concepts}
\begin{conceptbox}
  Key concept: Heterogeneous catalysis occurs at the interface...
\end{conceptbox}

\subsection{Surface Reactions} 
Detailed explanation of surface chemistry.

\section{Characterization Techniques}
Discussion of XPS, TEM, etc.

\section{Case Studies}
\begin{highlightbox}
  Key finding: The SMSI effect increased activity by 300\%.
\end{highlightbox}

\section{Conclusion}
Summary and outlook.
```

## 🔧 Troubleshooting

### Common Issues

**Issue**: "Font not found" error
- **Solution**: Ensure you're using LuaLaTeX, not pdfLaTeX

**Issue**: Missing logo or icon
- **Solution**: Place all required PDF files in the same directory as your `.tex` file

**Issue**: Chemical formulas not rendering
- **Solution**: Check that mhchem v4 is installed: `\usepackage[version=4]{mhchem}`

**Issue**: Overfull hbox warnings in two-column mode
- **Solution**: The template includes `\emergencystretch=2em` to minimize this. Rewrite long URLs or use `\url{}` command.

**Issue**: Bibliography not appearing
- **Solution**: Run the full compile sequence: lualatex → bibtex → lualatex → lualatex

### Getting Help

For template-specific questions:
- Open an issue on GitHub
- Email: catalysiseducation@gmail.com
- Check the [FAQ](https://catalysiseducation.substack.com/)

## 🤝 Contributing

We welcome contributions to improve this template! 

### How to Contribute

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Make your changes
4. Test compilation thoroughly
5. Commit your changes (`git commit -m 'Add improvement'`)
6. Push to the branch (`git push origin feature/improvement`)
7. Open a Pull Request

### Contribution Guidelines

- Maintain compatibility with LuaLaTeX
- Test on multiple platforms (Windows, macOS, Linux)
- Document new features in README
- Follow existing code style
- Update version number for significant changes

## 📄 License

This template is licensed under **CC BY-SA 4.0** (Creative Commons Attribution-ShareAlike 4.0 International).

You are free to:
- **Share** — copy and redistribute the template
- **Adapt** — remix, transform, and build upon the template

Under the following terms:
- **Attribution** — Give appropriate credit to Catalysis Education Newsletter
- **NonCommercial** — Not for commercial use

See [LICENSE](LICENSE) for full details.

## 📧 Contact

**Catalysis Education Newsletter**

- **Email**: catalysiseducation@gmail.com
- **Website**: https://catalysiseducation.substack.com/
- **GitHub**: https://github.com/catalysis-education

---

### Citation

If you use this template, please cite:

```bibtex
@misc{catalysis_education_template,
  title = {Catalysis Education Newsletter LaTeX Template},
  author = {{Catalysis Education Newsletter}},
  year = {2026},
  version = {4.0},
  url = {https://github.com/catalysis-education/latex-template}
}
```

---

**Version**: 4.0 (January 2026)  
**Last Updated**: February 2026

*For the latest version, visit our [GitHub repository](https://github.com/catalysis-education/latex-template)*
