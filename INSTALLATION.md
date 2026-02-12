# Installation Guide

Complete guide for setting up and using the Catalysis Education Newsletter LaTeX Template.

## Table of Contents

- [System Requirements](#system-requirements)
- [Installation Methods](#installation-methods)
  - [Method 1: Local Installation](#method-1-local-installation)
  - [Method 2: Overleaf](#method-2-overleaf)
  - [Method 3: Docker](#method-3-docker)
- [Required Files](#required-files)
- [Verification](#verification)
- [Troubleshooting](#troubleshooting)

## System Requirements

### Operating System
- **Windows**: 7 or later
- **macOS**: 10.12 (Sierra) or later
- **Linux**: Any modern distribution

### LaTeX Distribution

You need a complete LaTeX distribution with LuaLaTeX support:

#### TeX Live (Recommended for Linux/macOS)
- **Minimum Version**: TeX Live 2020
- **Recommended**: TeX Live 2023 or later
- **Download**: https://www.tug.org/texlive/

#### MiKTeX (Recommended for Windows)
- **Minimum Version**: MiKTeX 2020
- **Recommended**: MiKTeX 23.x or later
- **Download**: https://miktex.org/download

### Disk Space
- Minimum: 500 MB for template and examples
- Recommended: 5 GB for full LaTeX distribution

### Memory
- Minimum: 2 GB RAM
- Recommended: 4 GB RAM or more

## Installation Methods

### Method 1: Local Installation

#### Step 1: Install LaTeX Distribution

##### Windows (MiKTeX)

1. Download MiKTeX installer from https://miktex.org/download
2. Run the installer and choose "Complete" installation
3. During installation, select "Install missing packages on-the-fly: Yes"
4. Wait for installation to complete (~3-5 GB)

**Verify installation:**
```cmd
lualatex --version
```

##### macOS (TeX Live)

**Option A: MacTeX (Easy)**
1. Download MacTeX from https://www.tug.org/mactex/
2. Mount the .pkg file and run installer
3. Wait for installation (~7 GB)

**Option B: Homebrew**
```bash
brew install --cask mactex
```

**Verify installation:**
```bash
lualatex --version
```

##### Linux (TeX Live)

**Ubuntu/Debian:**
```bash
sudo apt update
sudo apt install texlive-full
```

**Fedora:**
```bash
sudo dnf install texlive-scheme-full
```

**Arch Linux:**
```bash
sudo pacman -S texlive-most
```

**Verify installation:**
```bash
lualatex --version
```

#### Step 2: Install Git (Optional but Recommended)

##### Windows
Download from https://git-scm.com/download/win

##### macOS
```bash
brew install git
```

##### Linux
```bash
# Ubuntu/Debian
sudo apt install git

# Fedora
sudo dnf install git

# Arch
sudo pacman -S git
```

#### Step 3: Download Template

**Option A: Using Git (Recommended)**
```bash
git clone https://github.com/catalysis-education/latex-template.git
cd latex-template
```

**Option B: Direct Download**
1. Visit https://github.com/catalysis-education/latex-template
2. Click "Code" → "Download ZIP"
3. Extract the ZIP file to your desired location

#### Step 4: Install Required Packages

The template uses many packages. Most are included in full LaTeX installations, but you may need to install some manually:

##### MiKTeX (Windows)
MiKTeX will prompt you to install missing packages automatically.

##### TeX Live (macOS/Linux)
If you installed the "full" version, all packages should be available. Otherwise:

```bash
sudo tlmgr update --self
sudo tlmgr install collection-fontsrecommended
sudo tlmgr install collection-latexextra
sudo tlmgr install fontawesome5
sudo tlmgr install mhchem
sudo tlmgr install chemfig
sudo tlmgr install chemmacros
```

#### Step 5: Verify Installation

```bash
cd latex-template
lualatex catalysis_education_template.tex
```

If successful, you should see `catalysis_education_template.pdf` created.

### Method 2: Overleaf

Overleaf is an online LaTeX editor that requires no local installation.

#### Step 1: Create Overleaf Account
1. Visit https://www.overleaf.com
2. Sign up for a free account

#### Step 2: Upload Template

**Option A: From GitHub**
1. In Overleaf, click "New Project"
2. Select "Import from GitHub"
3. Authorize Overleaf to access GitHub
4. Select the `catalysis-education/latex-template` repository

**Option B: Upload ZIP**
1. Download template as ZIP from GitHub
2. In Overleaf, click "New Project" → "Upload Project"
3. Upload the ZIP file

#### Step 3: Configure Compiler

1. Click the "Menu" button (top left)
2. Under "Settings", find "Compiler"
3. Select **"LuaLaTeX"** (important!)
4. Click "Recompile"

#### Step 4: Add Required Images

If images are missing:
1. Download from the GitHub repository:
   - `logodec_updated.pdf`
   - `orcid.pdf`
   - `ccby.pdf`
2. In Overleaf, click "Upload" icon
3. Select and upload the image files

### Method 3: Docker

Use Docker for a portable, isolated environment.

#### Step 1: Install Docker

Follow instructions at https://docs.docker.com/get-docker/

#### Step 2: Create Dockerfile

Create a file named `Dockerfile`:

```dockerfile
FROM texlive/texlive:latest

WORKDIR /workspace

# Install additional packages if needed
RUN tlmgr update --self && \
    tlmgr install fontawesome5 mhchem chemfig chemmacros

# Copy template files
COPY . /workspace

# Default command
CMD ["lualatex", "catalysis_education_template.tex"]
```

#### Step 3: Build Docker Image

```bash
docker build -t catalysis-latex .
```

#### Step 4: Run Compilation

```bash
docker run -v $(pwd):/workspace catalysis-latex
```

## Required Files

Ensure you have these files in your working directory:

### Essential Template Files
- `catalysis_education_template.tex` - Main template
- `example.bib` - Example bibliography (optional)

### Required Image Files
- `logodec_updated.pdf` - Newsletter logo
- `orcid.pdf` - ORCID icon
- `ccby.pdf` - Creative Commons license icon

### Optional Files
- `README.md` - Documentation
- `CONTRIBUTING.md` - Contribution guidelines
- `LICENSE` - License information

### Where to Get Image Files

**Option 1: From Repository**
Download from https://github.com/catalysis-education/latex-template/tree/main/images

**Option 2: Create Your Own**

**ORCID Icon:**
Download from https://orcid.org/trademark-and-id-display-guidelines

**Creative Commons Icon:**
Download from https://creativecommons.org/about/downloads/

**Newsletter Logo:**
Contact catalysiseducation@gmail.com for the official logo

## Verification

### Test Compilation

Create a minimal test file `test.tex`:

```latex
\documentclass{article}
\usepackage{fontspec}
\setmainfont{TeX Gyre Termes}

\begin{document}
Hello from LuaLaTeX!
\end{document}
```

Compile:
```bash
lualatex test.tex
```

### Check Package Installation

Test chemistry packages:

```latex
\documentclass{article}
\usepackage[version=4]{mhchem}
\usepackage{chemfig}

\begin{document}
Formula: \ce{H2O}

Structure: \chemfig{H-O-H}
\end{document}
```

### Check Font Installation

```bash
luaotfload-tool --list=*gyre*
```

You should see TeX Gyre fonts listed.

### Full Template Test

```bash
# Clean previous builds
rm -f *.aux *.log *.out *.bbl *.blg

# Full compilation with bibliography
lualatex catalysis_education_template.tex
bibtex catalysis_education_template
lualatex catalysis_education_template.tex
lualatex catalysis_education_template.tex

# Check for errors
grep -i error catalysis_education_template.log
```

## Troubleshooting

### Common Issues

#### Issue: "Font not found"

**Symptoms:**
```
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
!
! fontspec error: "font-not-found"
```

**Solutions:**

1. **Update font cache:**
   ```bash
   # Linux/macOS
   luaotfload-tool --update --force
   
   # Windows (MiKTeX)
   initexmf --update-fndb
   ```

2. **Install TeX Gyre fonts:**
   ```bash
   sudo tlmgr install tex-gyre
   sudo tlmgr install tex-gyre-math
   ```

3. **Install Source Serif:**
   ```bash
   sudo tlmgr install sourceserifpro
   ```

#### Issue: "Package not found"

**Symptoms:**
```
! LaTeX Error: File `package.sty' not found.
```

**Solutions:**

1. **Install missing package (TeX Live):**
   ```bash
   sudo tlmgr install packagename
   ```

2. **Install missing package (MiKTeX):**
   - MiKTeX should prompt automatically
   - Or manually: MiKTeX Console → Packages → Search and install

3. **Update package database:**
   ```bash
   # TeX Live
   sudo tlmgr update --self --all
   
   # MiKTeX
   mpm --update-db
   ```

#### Issue: "LuaLaTeX not found"

**Symptoms:**
```
bash: lualatex: command not found
```

**Solutions:**

1. **Check PATH (macOS/Linux):**
   ```bash
   echo $PATH | grep texlive
   
   # If not found, add to ~/.bashrc or ~/.zshrc:
   export PATH=/usr/local/texlive/2023/bin/x86_64-linux:$PATH
   ```

2. **Check PATH (Windows):**
   - Add `C:\texlive\2023\bin\win32` to system PATH
   - Or `C:\Program Files\MiKTeX\miktex\bin\x64`

3. **Reinstall LaTeX distribution**

#### Issue: Compilation hangs or is very slow

**Solutions:**

1. **Increase memory:**
   Edit `texmf.cnf` to increase `main_memory`

2. **Disable on-the-fly package installation:**
   In MiKTeX Console, change to "Always ask"

3. **Clear auxiliary files:**
   ```bash
   rm -f *.aux *.log *.out *.toc
   ```

#### Issue: "File not found" for images

**Solutions:**

1. **Check file locations:**
   ```bash
   ls -l *.pdf
   ```

2. **Use absolute paths temporarily:**
   ```latex
   \includegraphics[...]{/full/path/to/image.pdf}
   ```

3. **Check file permissions:**
   ```bash
   chmod 644 *.pdf
   ```

#### Issue: Bibliography not appearing

**Solutions:**

1. **Full compilation sequence:**
   ```bash
   lualatex file.tex
   bibtex file
   lualatex file.tex
   lualatex file.tex
   ```

2. **Check .bib file syntax:**
   Validate at https://www.bibtex.com/c/bibtex-format-checker/

3. **Check citations exist:**
   Ensure you have `\cite{...}` commands in your document

### Platform-Specific Issues

#### macOS: "Command not found"

Add to `~/.zshrc`:
```bash
export PATH=/Library/TeX/texbin:$PATH
```

#### Windows: Permission denied

Run Command Prompt as Administrator

#### Linux: Missing fonts

```bash
sudo apt install fonts-texgyre
sudo fc-cache -f -v
```

## Getting Help

### Documentation
- Template README: https://github.com/catalysis-education/latex-template
- LaTeX Wikibook: https://en.wikibooks.org/wiki/LaTeX
- TeX Stack Exchange: https://tex.stackexchange.com/

### Support Channels
- GitHub Issues: https://github.com/catalysis-education/latex-template/issues
- Email: catalysiseducation@gmail.com
- TeX Stack Exchange: Tag questions with `lualatex` and `catalysis`

### Reporting Bugs

When reporting installation issues, include:
1. Operating system and version
2. LaTeX distribution and version (`lualatex --version`)
3. Full error message
4. Output of `echo $PATH` (macOS/Linux) or PATH variable (Windows)
5. List of installed packages (`tlmgr list --only-installed` or MiKTeX packages)

---

**Installation complete!** You're ready to create your first article.

For usage instructions, see [README.md](README.md)
