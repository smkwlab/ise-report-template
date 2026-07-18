# CLAUDE.md

HTML-based academic report template for Information Science Exercise I & II courses at Kyushu Sangyo University. Features comprehensive quality management and automated validation workflows.

## Quick Start

### Template Usage
1. Students create their repository with the automated setup script
   (document type `ise`); see the [README](README.md) for the current
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
2. **DevContainer Development**: VS Code with real-time feedback
3. **Pull Request Submission**: Automated quality validation
4. **Completion**: mark the accepted version with the `final` tag

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
latex-environment (DevContainer base)
    ↓
ise-report-template (HTML specialization)
    ├── HTML5/CSS focus
    ├── Web accessibility emphasis
    └── textlint quality management
```

## Detailed Documentation

- **[Development Guide](docs/CLAUDE-DEVELOPMENT.md)** - Architecture, workflow inventory, quality automation, HTML examples
- **[Troubleshooting](docs/CLAUDE-TROUBLESHOOTING.md)** - Common issues, debug commands, performance optimization

The student-facing submission flow is documented in the [README](README.md).