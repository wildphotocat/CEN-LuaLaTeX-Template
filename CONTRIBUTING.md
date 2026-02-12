# Contributing to Catalysis Education Newsletter LaTeX Template

Thank you for your interest in contributing to the Catalysis Education Newsletter LaTeX template! This document provides guidelines for contributing to the project.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Development Setup](#development-setup)
- [Contribution Guidelines](#contribution-guidelines)
- [Style Guide](#style-guide)
- [Testing](#testing)
- [Submitting Changes](#submitting-changes)

## Code of Conduct

This project and everyone participating in it is governed by our commitment to fostering an open and welcoming environment. By participating, you are expected to uphold professional and respectful behavior.

### Our Standards

- Using welcoming and inclusive language
- Being respectful of differing viewpoints and experiences
- Gracefully accepting constructive criticism
- Focusing on what is best for the community
- Showing empathy towards other community members

## How Can I Contribute?

### Reporting Bugs

Before creating bug reports, please check existing issues to avoid duplicates. When creating a bug report, include:

- **Clear title and description**
- **Exact steps to reproduce** the issue
- **Expected behavior** vs. actual behavior
- **LaTeX distribution and version** (TeX Live, MiKTeX, etc.)
- **Operating system** (Windows, macOS, Linux)
- **Minimal working example** (MWE) demonstrating the issue
- **Error messages** (full log if possible)

### Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion, include:

- **Clear title and description**
- **Use case** explaining why this enhancement would be useful
- **Example implementation** (if you have one in mind)
- **Alternative solutions** you've considered

### Pull Requests

We actively welcome your pull requests:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Make your changes following our style guide
4. Test thoroughly on multiple platforms
5. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
6. Push to the branch (`git push origin feature/AmazingFeature`)
7. Open a Pull Request

## Development Setup

### Prerequisites

- TeX Live 2020 or later / MiKTeX 2020 or later
- LuaLaTeX compiler
- Git
- Text editor or LaTeX IDE

### Local Setup

```bash
# Clone your fork
git clone https://github.com/YOUR-USERNAME/latex-template.git
cd latex-template

# Add upstream remote
git remote add upstream https://github.com/catalysis-education/latex-template.git

# Create a branch for your changes
git checkout -b feature/your-feature-name
```

### Testing Your Changes

```bash
# Compile the template
lualatex catalysis_education_template.tex

# Check for errors
grep -i "error\|warning" catalysis_education_template.log

# Test bibliography
bibtex catalysis_education_template
lualatex catalysis_education_template.tex
lualatex catalysis_education_template.tex
```

## Contribution Guidelines

### Types of Contributions

We welcome the following types of contributions:

#### 1. Bug Fixes
- Fix compilation errors
- Resolve formatting issues
- Correct typos in documentation

#### 2. Feature Enhancements
- New colored box styles
- Additional chemistry packages integration
- Improved layout options
- Enhanced bibliography styles

#### 3. Documentation
- Improve README clarity
- Add usage examples
- Create video tutorials
- Translate documentation

#### 4. Testing
- Test on different platforms
- Test with different LaTeX distributions
- Report compatibility issues

### What We Don't Accept

- Changes that break backward compatibility without discussion
- Features that work only with specific LaTeX distributions
- Contributions that remove existing functionality
- Undocumented changes to core template structure

## Style Guide

### LaTeX Code Style

#### Comments
```latex
% Single-line comment explaining what follows
% More detailed explanation if needed

% ---- SECTION HEADER ----
% Group related code under clear section headers
```

#### Spacing
```latex
% Good: Clear spacing around blocks
\usepackage{package1}
\usepackage{package2}

\newcommand{\mycommand}{...}

% Bad: Cramped code
\usepackage{package1}\usepackage{package2}\newcommand{\mycommand}{...}
```

#### Command Definition
```latex
% Good: Clear parameter names and documentation
% Define command for author ORCID links
% Usage: \orcid{0000-0000-0000-0000}
\newcommand{\orcid}[1]{%
  \href{https://orcid.org/#1}{...}%
}

% Bad: Unclear purpose and parameters
\newcommand{\x}[1]{\href{https://orcid.org/#1}{...}}
```

#### Package Loading
```latex
% Group packages by functionality with clear comments

% ---- FONTS AND TYPOGRAPHY ----
\usepackage{fontspec}
\usepackage{microtype}

% ---- CHEMISTRY PACKAGES ----
\usepackage[version=4]{mhchem}
\usepackage{chemfig}
```

### Documentation Style

#### Markdown Formatting
- Use clear headers (H2 for main sections, H3 for subsections)
- Include code blocks with language specification
- Add examples where helpful
- Use bullet points for lists
- Keep line length reasonable (~80-100 characters)

#### Example Format
```markdown
### Feature Name

Brief description of the feature.

**Usage:**
```latex
\begin{feature}
  content
\end{feature}
```

**Output:** Description of what this produces.
```

## Testing

### Compilation Testing

Test your changes with:

```bash
# Clean build
rm -f *.aux *.log *.out *.bbl *.blg
lualatex catalysis_education_template.tex

# Check for errors
echo $?  # Should output 0 for success

# Full bibliography test
lualatex catalysis_education_template.tex
bibtex catalysis_education_template
lualatex catalysis_education_template.tex
lualatex catalysis_education_template.tex
```

### Cross-Platform Testing

If possible, test on:
- Windows (TeX Live and MiKTeX)
- macOS (TeX Live)
- Linux (TeX Live)

### Regression Testing

Ensure your changes don't break:
- Existing example compilations
- Two-column layout
- Bibliography formatting
- Hyperlink functionality
- Chemistry formula rendering
- Figure and table placement

## Submitting Changes

### Commit Messages

Follow conventional commit format:

```
type(scope): brief description

Detailed explanation of changes (if needed).

Fixes #issue_number (if applicable)
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Formatting changes
- `refactor`: Code restructuring
- `test`: Adding tests
- `chore`: Maintenance tasks

**Examples:**
```
feat(boxes): add new warning box style

Add a new orange warning box for moderate cautions that are
less severe than the red caution box.

fix(bibliography): correct ACS citation format

The superscript citations were not compressing properly.
Updated natbib configuration to fix this.

Fixes #42

docs(readme): add installation instructions for Overleaf

Added step-by-step guide for using the template on Overleaf.
```

### Pull Request Process

1. **Update Documentation**: Update README.md with any new features
2. **Test Thoroughly**: Ensure all tests pass
3. **Update Changelog**: Add entry to CHANGELOG.md (if exists)
4. **Clean Commit History**: Squash commits if needed
5. **Fill PR Template**: Provide clear description of changes
6. **Request Review**: Tag maintainers for review

### Pull Request Template

```markdown
## Description
Brief description of changes

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Documentation update
- [ ] Performance improvement

## Testing
- [ ] Tested on TeX Live
- [ ] Tested on MiKTeX
- [ ] Cross-platform testing completed
- [ ] No compilation errors
- [ ] No new warnings

## Checklist
- [ ] Code follows style guidelines
- [ ] Self-review completed
- [ ] Documentation updated
- [ ] No breaking changes (or documented if needed)

## Screenshots/Examples
(If applicable)
```

## Review Process

### What to Expect

- Initial review within 1 week
- Feedback on code quality, testing, and documentation
- Possible requests for changes
- Merge once approved by maintainer

### Review Criteria

Reviewers will check:
- Code quality and clarity
- Compatibility with LuaLaTeX
- Documentation completeness
- Testing coverage
- No breaking changes (or properly documented)
- Follows project style guide

## Recognition

Contributors will be:
- Listed in CONTRIBUTORS.md
- Mentioned in release notes
- Acknowledged in the template documentation

## Questions?

- Open an issue for questions
- Email: catalysiseducation@gmail.com
- Check existing discussions

---

**Thank you for contributing to the Catalysis Education Newsletter template!**

Your contributions help improve catalysis education worldwide.
