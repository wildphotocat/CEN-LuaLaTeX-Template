# GitHub Repository Setup Guide

Instructions for setting up the Catalysis Education Newsletter LaTeX Template repository on GitHub.

## Repository Creation

### Step 1: Create New Repository

1. Go to https://github.com/new
2. Set repository details:
   - **Owner**: catalysis-education (or your organization)
   - **Repository name**: `latex-template`
   - **Description**: "Official LaTeX template for Catalysis Education Newsletter submissions"
   - **Visibility**: Public
   - **Initialize**: Don't initialize with README (we have our own)

### Step 2: Upload Files

You have two options:

#### Option A: Using Git Command Line

```bash
# Initialize local repository
cd /path/to/template/files
git init

# Add all files
git add .

# Initial commit
git commit -m "Initial commit: LaTeX template v4.0"

# Add remote repository
git remote add origin https://github.com/catalysis-education/latex-template.git

# Push to GitHub
git branch -M main
git push -u origin main
```

#### Option B: Using GitHub Web Interface

1. On the repository page, click "uploading an existing file"
2. Drag and drop all files from your local directory
3. Write commit message: "Initial commit: LaTeX template v4.0"
4. Click "Commit changes"

## Repository Configuration

### Step 3: Configure Repository Settings

1. Go to repository Settings → General
2. Set default branch to `main`
3. Enable features:
   - ✅ Issues
   - ✅ Projects
   - ✅ Wiki
   - ✅ Discussions (optional)

### Step 4: Configure Branch Protection

1. Settings → Branches
2. Add branch protection rule for `main`:
   - ✅ Require pull request reviews before merging
   - ✅ Require status checks to pass before merging
   - ✅ Require branches to be up to date before merging
   - ✅ Include administrators

### Step 5: Set Up Topics

Settings → scroll to "Topics", add:
- `latex`
- `template`
- `catalysis`
- `education`
- `academic-writing`
- `chemistry`
- `lualatex`

### Step 6: Configure GitHub Pages (Optional)

For documentation hosting:

1. Settings → Pages
2. Source: Deploy from branch
3. Branch: `main` / `docs` folder (if you create one)
4. Save

## Enable GitHub Actions

The repository includes a workflow file that automatically builds the template on every push.

### Step 7: Enable Actions

1. Go to repository Actions tab
2. Click "I understand my workflows, go ahead and enable them"
3. The build workflow should appear

### Step 8: Verify Build

1. Make a small change and push
2. Go to Actions tab
3. Check that build completes successfully
4. Download PDF artifact to verify

## Set Up Issue Templates

The repository includes:
- `.github/ISSUE_TEMPLATE/bug_report.md`
- `.github/ISSUE_TEMPLATE/feature_request.md`

These are automatically available when users create issues.

## Set Up Labels

Create these labels for issue management:

| Label | Color | Description |
|-------|-------|-------------|
| bug | #d73a4a | Something isn't working |
| enhancement | #a2eeef | New feature or request |
| documentation | #0075ca | Improvements or additions to documentation |
| good first issue | #7057ff | Good for newcomers |
| help wanted | #008672 | Extra attention is needed |
| question | #d876e3 | Further information is requested |
| wontfix | #ffffff | This will not be worked on |
| duplicate | #cfd3d7 | This issue or pull request already exists |
| invalid | #e4e669 | This doesn't seem right |
| compatibility | #fbca04 | Platform or distribution compatibility |
| compilation | #ff6b6b | Compilation errors or warnings |

## Repository Structure

```
latex-template/
├── .github/
│   ├── workflows/
│   │   └── build.yml
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.md
│   │   └── feature_request.md
│   └── pull_request_template.md
├── catalysis_education_template.tex
├── example.bib
├── README.md
├── QUICKSTART.md
├── INSTALLATION.md
├── CONTRIBUTING.md
├── CHANGELOG.md
├── LICENSE
└── .gitignore
```

## Add Required Images

Create an `images/` directory and add:
- `logodec_updated.pdf` - Newsletter logo
- `orcid.pdf` - ORCID icon
- `ccby.pdf` - Creative Commons icon

These files should be added separately as they contain specific branding.

## Create Release

### Step 9: Create Initial Release

1. Go to repository → Releases
2. Click "Create a new release"
3. Tag: `v4.0.0`
4. Title: "LaTeX Template v4.0.0 - Initial Release"
5. Description:
   ```markdown
   ## Catalysis Education Newsletter LaTeX Template v4.0.0
   
   Initial public release of the official template.
   
   ### Features
   - LuaLaTeX support with modern fonts
   - Four colored highlight boxes
   - Integrated ORCID and social media links
   - ACS-style bibliography
   - Comprehensive documentation
   
   ### Requirements
   - LuaLaTeX
   - TeX Live 2020+ or MiKTeX 2020+
   
   ### Documentation
   - Quick Start: See QUICKSTART.md
   - Full Guide: See README.md
   - Installation: See INSTALLATION.md
   
   ### Download
   Download all files and follow installation instructions.
   ```
6. Attach compiled PDF as asset (optional)
7. Click "Publish release"

## Configure Webhooks (Optional)

For automated notifications:

1. Settings → Webhooks
2. Add webhook for Slack/Discord (if applicable)
3. Configure events: pushes, pull requests, issues

## Set Up Projects (Optional)

For roadmap and feature tracking:

1. Projects tab → New project
2. Create boards:
   - Template Development
   - Documentation
   - Bug Fixes
3. Add columns: To Do, In Progress, Done

## Repository About Section

Edit the About section (top right of main page):

- **Description**: "Official LaTeX template for Catalysis Education Newsletter submissions. Modern, professional format with chemistry support."
- **Website**: https://catalysiseducation.substack.com/
- **Topics**: latex, template, catalysis, education, academic-writing, chemistry, lualatex

## README Badges

Consider adding these badges to README.md:

```markdown
![Build Status](https://github.com/catalysis-education/latex-template/workflows/Build%20LaTeX%20Template/badge.svg)
![Version](https://img.shields.io/badge/version-4.0.0-blue)
![License](https://img.shields.io/badge/license-CC--BY--NC--4.0-green)
![LaTeX](https://img.shields.io/badge/LaTeX-LuaLaTeX-orange)
```

## Community Files

The repository includes:
- ✅ README.md
- ✅ LICENSE
- ✅ CONTRIBUTING.md
- ✅ Code of Conduct (recommended to add)
- ✅ Issue templates
- ✅ Pull request template

Consider adding:
- `CODE_OF_CONDUCT.md` - Community guidelines
- `SECURITY.md` - Security policy
- `SUPPORT.md` - Support resources

## Maintenance

### Regular Tasks

1. **Monitor Issues**: Respond to issues within 1 week
2. **Review PRs**: Review pull requests promptly
3. **Update Dependencies**: Keep LaTeX packages current
4. **Update Documentation**: Keep README and guides current
5. **Create Releases**: Version releases for significant changes

### Version Numbering

Follow Semantic Versioning (semver):
- **MAJOR**: Breaking changes (e.g., 4.0.0 → 5.0.0)
- **MINOR**: New features, backwards compatible (e.g., 4.0.0 → 4.1.0)
- **PATCH**: Bug fixes (e.g., 4.0.0 → 4.0.1)

## Post-Setup Checklist

- [ ] Repository created on GitHub
- [ ] All files uploaded
- [ ] Branch protection configured
- [ ] Topics/labels configured
- [ ] GitHub Actions enabled and passing
- [ ] Initial release created (v4.0.0)
- [ ] README badges added
- [ ] About section filled
- [ ] Image files added to repository
- [ ] Documentation reviewed and accurate
- [ ] Links in README verified
- [ ] License file correct
- [ ] Contributing guidelines clear

## Promotion

After setup:

1. Announce on Catalysis Education Newsletter
2. Share on social media
3. Post on relevant forums (TeX Stack Exchange, r/LaTeX)
4. Add to awesome-latex lists
5. Submit to CTAN (optional)

## Support Channels

Set up:
- GitHub Issues for bug reports
- GitHub Discussions for Q&A (optional)
- Email: catalysiseducation@gmail.com
- Documentation website (optional)

---

## Quick Setup Script

```bash
#!/bin/bash
# Quick setup script for repository

# Create repository on GitHub first, then:

cd /path/to/template/files
git init
git add .
git commit -m "Initial commit: LaTeX template v4.0.0"
git branch -M main
git remote add origin https://github.com/catalysis-education/latex-template.git
git push -u origin main

# Create and push tags
git tag -a v4.0.0 -m "Initial release: LaTeX template v4.0.0"
git push origin v4.0.0

echo "Setup complete!"
echo "Next steps:"
echo "1. Configure branch protection on GitHub"
echo "2. Enable GitHub Actions"
echo "3. Create release from tag v4.0.0"
echo "4. Add required image files"
```

---

**Repository setup complete!** Your template is now ready for the community.

For questions: catalysiseducation@gmail.com
