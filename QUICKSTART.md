# Quick Start Guide

Get up and running with the Catalysis Education Newsletter template in 5 minutes!

## Prerequisites

✅ LuaLaTeX installed ([Installation Guide](INSTALLATION.md))  
✅ Template files downloaded  
✅ Required image files (orcid.pdf, ccby.pdf, logodec_updated.pdf)

## Step 1: Open the Template (30 seconds)

Open `catalysis_education_template.tex` in your LaTeX editor.

## Step 2: Fill in Metadata (2 minutes)

Find this section near line 360:

```latex
% =========================================
% FILL IN YOUR ARTICLE INFORMATION
% =========================================
```

Update these fields:

```latex
\malar{1}                          % Volume number
\petal{1}                          % Issue number  
\yearval{2026}                     % Publication year
\articletype{Educational Article}  % Your article type

\title{Your Article Title Here}

\author{%
  \textbf{Your Name}\textsuperscript{1\,\href{mailto:your.email@edu}{\faEnvelope}} 
  \orcid{0000-0000-0000-0000}
  \href{https://scholar.google.com/...}{\small \faGraduationCap} 
  \href{https://www.linkedin.com/...}{\small \faLinkedin}
}

\affiliation{%
  \textsuperscript{1}Your Department, University, City, Country
}

\keywords{keyword1, keyword2, keyword3, keyword4, keyword5}
```

## Step 3: Write Your Content (varies)

### Abstract (Line ~430)
Replace the placeholder abstract with yours (150-250 words):

```latex
\noindent
\small
Your abstract text goes here. Keep it concise and focused...
\vspace{0.3cm}
```

### Main Content (After `\twocolumn`)
Replace the example sections with your content:

```latex
\section{Introduction}
Your introduction text...

\section{Background}
Background information...

\section{Results}
Your results...

\section{Conclusion}
Your conclusions...
```

## Step 4: Add Chemistry (as needed)

Use mhchem for formulas:

```latex
\ce{H2O}           % Water
\ce{CO2}           % Carbon dioxide  
\ce{2H2 + O2 -> 2H2O}  % Reaction
```

## Step 5: Insert Figures (optional)

For full-width figures:

```latex
\begin{figure*}[t]
  \centering
  \includegraphics[width=0.8\textwidth]{your_figure.pdf}
  \caption{Your caption here.}
  \label{fig:example}
\end{figure*}
```

Reference in text: `See Figure~\ref{fig:example}...`

## Step 6: Add References (optional)

Create or edit `example.bib`:

```bibtex
@article{smith2025,
  author  = {Smith, John},
  title   = {Article Title},
  journal = {Journal Name},
  year    = {2025},
  volume  = {10},
  pages   = {1-10},
  doi     = {10.1234/example}
}
```

Cite in text:

```latex
As shown by Smith\cite{smith2025}, ...
```

Enable bibliography at end:

```latex
\bibliographystyle{achemso}
\bibliography{example}
```

## Step 7: Compile (1 minute)

### Using Command Line:

```bash
lualatex catalysis_education_template.tex
bibtex catalysis_education_template    # Only if you have citations
lualatex catalysis_education_template.tex
lualatex catalysis_education_template.tex
```

### Using LaTeX Editor:

1. Select **LuaLaTeX** as compiler
2. Click "Compile" or press F1/Cmd+R
3. View the PDF output

### Using Overleaf:

1. Menu → Compiler → Select **LuaLaTeX**
2. Click "Recompile"
3. View PDF in right panel

## Common First-Time Issues

### ❌ "Font not found"
**Solution**: Make sure you're using LuaLaTeX, not pdfLaTeX

### ❌ "File not found: logodec_updated.pdf"
**Solution**: Place all required image files in same directory as .tex file

### ❌ Compilation hangs
**Solution**: Close and reopen your editor, clear auxiliary files

### ❌ Chemistry formulas not rendering  
**Solution**: Check you have `\usepackage[version=4]{mhchem}` in preamble

## Tips for Success

### 🎯 Start Simple
Begin with just title, authors, and a basic introduction. Add complexity gradually.

### 📝 Use Colored Boxes
Highlight important concepts:

```latex
\begin{conceptbox}
  Key concept explanation here.
\end{conceptbox}
```

### 🔗 Check All Links
Verify your ORCID, Google Scholar, and LinkedIn URLs work.

### 💾 Save Often
Save your .tex file frequently during editing.

### 🧪 Test Compile Regularly
Don't wait until you're done to compile. Test every few paragraphs.

## Example Workflow

```latex
% 1. Update metadata (2 min)
\title{My Article}
\author{...}

% 2. Write abstract (5 min)
\noindent\small
My abstract...

% 3. Write introduction (15 min)
\section{Introduction}
Text...

% 4. Compile to check (1 min)
% lualatex catalysis_education_template.tex

% 5. Add more sections (varies)
\section{Methods}
\section{Results}

% 6. Add figures (10 min)
\begin{figure*}...

% 7. Add references (10 min)
\cite{...}

% 8. Final compile (2 min)
% Full sequence with bibliography
```

## Next Steps

Once you're comfortable with basics:

1. ✅ Read full [README.md](README.md) for all features
2. ✅ Review [Author Guidelines](#) in the template
3. ✅ Explore colored boxes and special features
4. ✅ Add complex figures and tables
5. ✅ Customize for your specific needs

## Getting Help

- 📖 Full documentation: [README.md](README.md)
- 🛠️ Installation help: [INSTALLATION.md](INSTALLATION.md)
- 🐛 Report issues: [GitHub Issues](https://github.com/catalysis-education/latex-template/issues)
- 📧 Email support: catalysiseducation@gmail.com

## Submission Checklist

Before submitting your article:

- [ ] Compiled successfully with LuaLaTeX
- [ ] All metadata fields completed
- [ ] ORCID and social links verified
- [ ] Abstract is 150-250 words
- [ ] 5-8 keywords provided
- [ ] All figures and tables referenced in text
- [ ] Chemistry formulas use `\ce{}`
- [ ] Bibliography formatted correctly
- [ ] No compilation errors
- [ ] All required files included

---

**You're ready to go!** 🚀

For detailed information, see the [complete README](README.md).
