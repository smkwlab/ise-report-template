# CLAUDE.md

HTML-based academic report template for Information Science Exercise I & II courses at Kyushu Sangyo University. Features comprehensive quality management and automated validation workflows.

## Quick Start

### Template Usage
1. Use as GitHub template to create personal repository
2. Naming: `k99rs999-ise-report1` (student ID + course identifier)
3. Open in VS Code with DevContainer support
4. Start editing `index.html` with real-time quality feedback

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
1. **Branch Creation**: `1st-draft`, `2nd-draft` for each submission
2. **DevContainer Development**: VS Code with real-time feedback
3. **Server Deployment**: Upload to www-st for web accessibility
4. **Pull Request Submission**: Automated quality validation

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

- **[Development Guide](docs/CLAUDE-DEVELOPMENT.md)** - Architecture, quality automation, technical configuration
- **[Troubleshooting](docs/CLAUDE-TROUBLESHOOTING.md)** - Common issues, debug commands, performance optimization
- **[Workflows & Examples](docs/CLAUDE-WORKFLOWS.md)** - Student workflows, development examples, GitHub integration