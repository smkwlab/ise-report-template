# CLAUDE.md

HTML-based academic report template for Information Science Exercise I & II courses at Kyushu Sangyo University. Features comprehensive quality management and automated validation workflows.

## Quick Start

### Template Usage
1. Students create their repository with the automated setup script
   (document type `ise`); see the [template README](.github/README.md) for the current
   one-liner. Repository naming (`k99rs999-ise-report1`) is handled by the
   script.
2. Open in VS Code with DevContainer support
3. Start editing `index.html` with real-time quality feedback

### Quality Features
- **textlint Integration**: Real-time Japanese writing validation
- **HTML5 Compliance**: W3C validation and accessibility checks
- **Automated Reviews**: GitHub Actions quality reports
- **Academic Standards**: である調 enforcement, 100-character limit

## Repository Structure

```
ise-report-template/
├── .devcontainer/          # DevContainer configuration
├── .github/workflows/      # Quality automation
├── .textlintrc            # Japanese writing rules
├── .htmlhintrc            # HTML quality rules
├── index.html             # Main report template
├── sample-index.html      # Usage examples
├── style.css              # Stylesheet
└── CLAUDE.md              # This file
```

## Technology Stack

- **textlint**: Japanese academic writing validation
- **html5validator**: W3C HTML5 compliance checking
- **htmlhint**: HTML quality and accessibility validation
- **DevContainer**: Alpine Linux + Node.js environment

## Educational Goals

- HTML5 semantic markup proficiency
- Japanese academic writing standards (である調)
- Version control workflow learning
- Quality-driven development practices

## Student Workflow

### Development Process
1. **Draft branches**: `0th-draft` exists at repository creation; each PR
   auto-creates the next draft branch (see README)
2. **PR base**: the previous draft branch (`main` for `0th-draft`), so the diff
   shows only what changed in that draft
3. **DevContainer Development**: VS Code with real-time feedback
4. **Pull Request Submission**: Automated quality validation
5. **Server Deployment**: upload to the course web server www-st
   (README「Webサーバ（www-st）への公開」; timing per instructor)
6. **Completion**: mark the accepted version with the `final` tag

### Course Applications
- **Information Science Exercise I**: Programming exercise reports, algorithm analysis
- **Information Science Exercise II**: Team project documentation, integration analysis

## Quality Standards

- **Sentence length**: Maximum 100 characters
- **Writing style**: である調 (formal Japanese)
- **Technical terms**: JavaScript, HTML, CSS, GitHub, LaTeX, VS Code
- **Accessibility**: Required alt attributes, semantic structure

## Ecosystem Integration

### Template Relationship
```
ise-report-template (HTML specialization)
    ├── HTML5/CSS focus
    ├── Web accessibility emphasis
    ├── textlint quality management
    └── its own DevContainer (see below)
```

### Why the DevContainer is built here

Every other template in the ecosystem uses the prebuilt
`ghcr.io/smkwlab/texlive-ja-textlint` image. This one builds its own from
`alpine` and installs textlint with `npm ci` (`.devcontainer/Dockerfile`).

**This repository produces HTML, not LaTeX.** There are no `.tex` files in it,
so a TeXLive image has nothing to offer here and would make students pull a
full TeX distribution to lint Japanese prose.

This has been decided more than once, so it is written down here. The reasons
it keeps getting re-proposed, and why none of them override the above:

- `.devcontainer/package.json` currently lists the same nine textlint packages
  as the image's own manifest. Identical contents are not a reason to take the
  heavy image; the overlap is textlint, which is the only part this repository
  needs.
- This is the only repository in the ecosystem with an npm lockfile, so it is
  the only one that accumulates npm advisories. That cost belongs to this
  decision — fix it inside the decision (keep the lock file fresh), not by
  reversing it.
- `.textlintrc` still enables the `latex2e` plugin and has an override for
  `*.tex`. Those are leftovers from the LaTeX templates this configuration was
  copied from; they match no files here.

## Detailed Documentation

- **[Development Guide](docs/CLAUDE-DEVELOPMENT.md)** - Architecture, workflow inventory, quality automation, HTML examples
- **[Troubleshooting](docs/CLAUDE-TROUBLESHOOTING.md)** - Common issues, debug commands, performance optimization

The student-facing submission flow is documented in the [template README](.github/README.md).

## Which README is shown where

GitHub resolves READMEs in the order `.github/` -> root -> `docs/`, and
student-repo-management removes `.github/README.md` at repository creation.
The two files therefore surface in exactly one place each:

- **[.github/README.md](.github/README.md)** - Template documentation (setup, writing
  procedure). Shown on this repository's front page; deleted in student repositories.
- **[README.md](README.md)** - Author-information template (name, student ID, title)
  filled in by the student. Shown on the student repository's front page.

Links out of `.github/README.md` may be relative because it only ever renders here.
Files that survive into student repositories must reference it by absolute URL.
