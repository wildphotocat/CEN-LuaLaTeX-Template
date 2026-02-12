# Changelog

All notable changes to the Catalysis Education Newsletter LaTeX Template will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Planned
- Additional color box styles
- Support for more bibliography formats
- Enhanced figure and table templates
- Video tutorials for template usage

## [4.0.0] - 2026-01-15

### Added
- Complete rewrite for LuaLaTeX compatibility
- Source Serif 4 font integration with optical sizing
- Four colored highlight boxes (Concept, Note, Highlight, Caution)
- Integrated ORCID, Google Scholar, and LinkedIn author links
- FontAwesome5 icons for social media links
- Two-line footer format with DOI on separate line
- "Broader Context" editorial commentary box
- "Read Online" button for HTML versions
- Open Access CC BY-NC 4.0 badge
- Automated page styles for first page and content pages
- Support for article types (Educational Article, Concept Note, Paper Commentary, Teaching Material)
- Enhanced chemistry package integration (mhchem v4, chemfig, chemmacros)
- Comprehensive author guidelines in template
- Line numbering for review process

### Changed
- Switched from pdfLaTeX to LuaLaTeX for better font support
- Updated font family to TeX Gyre (Termes, Heros, Cursor)
- Redesigned header with centered logo
- Improved two-column layout with better spacing
- Enhanced color scheme with professional blues and grays
- Modernized table styles with booktabs
- Updated bibliography style to ACS format

### Fixed
- Overfull hbox issues in two-column layout
- Font scaling in colored boxes
- Hyperlink colors for better readability
- Section heading spacing
- Author information formatting

### Removed
- Dependency on obsolete packages
- Hard-coded personal information
- Unnecessary complexity in preamble

## [3.0.0] - 2025-06-01

### Added
- Basic two-column layout
- Simple header and footer
- Chemistry package support
- Bibliography integration

### Changed
- Updated to modern LaTeX syntax
- Improved figure handling

## [2.0.0] - 2024-12-01

### Added
- Custom title page
- Author affiliation support
- Basic hyperlinks

## [1.0.0] - 2024-06-01

### Added
- Initial release
- Basic single-column template
- Simple formatting options
- Standard LaTeX article class

---

## Version History Summary

| Version | Date       | Major Changes                          |
|---------|------------|----------------------------------------|
| 4.0.0   | 2026-01-15 | LuaLaTeX, modern fonts, colored boxes  |
| 3.0.0   | 2025-06-01 | Two-column layout, chemistry packages  |
| 2.0.0   | 2024-12-01 | Custom title, author affiliations      |
| 1.0.0   | 2024-06-01 | Initial release                        |

---

## Migration Guides

### Migrating from 3.x to 4.0

**Breaking Changes:**
1. **Compiler**: Must now use LuaLaTeX instead of pdfLaTeX
2. **Fonts**: New font requirements (TeX Gyre family, Source Serif 4)
3. **Author format**: New format with ORCID and social links

**Migration Steps:**
```latex
% Old (v3.x)
\author{John Doe}
\affiliation{University}

% New (v4.0)
\author{%
  \textbf{John Doe}\textsuperscript{1\,\href{mailto:email}{\faEnvelope}} 
  \orcid{0000-0000-0000-0000}
  \href{...}{\small \faGraduationCap}
}
\affiliation{%
  \textsuperscript{1}Department, University, City, Country
}
```

### Migrating from 2.x to 3.0

**Breaking Changes:**
1. Layout changed from single-column to two-column
2. New chemistry package requirements

**Migration Steps:**
1. Update `\documentclass` options
2. Add `\twocolumn` before main content
3. Use `figure*` for full-width figures

---

## Deprecation Notices

### Version 4.0
- **pdfLaTeX support**: No longer maintained, use LuaLaTeX
- **Old author format**: Use new format with social links

### Version 3.0
- **Single-column layout**: No longer the default

---

## Contributors

We thank all contributors who have helped improve this template:

### Version 4.0
- Template redesign and modernization
- Enhanced documentation
- GitHub repository setup

### Previous Versions
- Initial template development
- Chemistry package integration
- Layout improvements

---

## Reporting Issues

Found a bug or have a suggestion? Please:
1. Check existing issues on GitHub
2. Create a new issue with details
3. Use the issue template provided

---

**For the latest version**: [GitHub Repository](https://github.com/catalysis-education/latex-template)

**Questions?** Email: catalysiseducation@gmail.com
