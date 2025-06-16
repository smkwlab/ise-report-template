# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with the Information Science Exercise (ISE) Report Template.

## Repository Overview

This is the **Information Science Exercise Report Template** - an HTML-based academic report template specifically designed for Information Science Exercise I & II courses at Kyushu Sangyo University. It features comprehensive quality management systems and automated validation workflows.

## Key Purpose

### Primary Function
- **Course Reports**: Template for Information Science Exercise I/II student reports
- **HTML Proficiency**: Develops web technology skills alongside academic writing
- **Quality Automation**: Comprehensive quality assurance with automated validation

### Educational Goals
- HTML5 semantic markup proficiency
- Japanese academic writing standards
- Version control workflow learning
- Quality-driven development practices

## Repository Structure

```
ise-report-template/
├── .devcontainer/          # DevContainer configuration
│   ├── Dockerfile         # Alpine + textlint environment
│   └── package.json       # textlint dependencies
├── .github/workflows/      # Quality automation
│   ├── html-validation.yml # HTML5/CSS/accessibility validation
│   ├── release.yml        # PDF generation workflow
│   └── autoassignees.yml  # Automatic review assignment
├── .textlintrc            # Unified textlint configuration (HTML/MD/LaTeX)
├── .htmlhintrc            # HTML quality rules
├── .yamllint.yml          # YAML workflow validation
├── index.html             # Main report template
├── sample-index.html      # Usage examples
├── style.css              # Stylesheet
└── CLAUDE.md              # This file
```

## Key Technologies

### Quality Management Stack
- **textlint**: Japanese academic writing validation
- **html5validator**: W3C HTML5 compliance checking
- **htmlhint**: HTML quality and accessibility validation
- **yamllint**: Workflow configuration validation

### Development Environment
- **DevContainer**: Alpine Linux + Node.js + textlint
- **VS Code Extensions**: Live Server, textlint, GitHub integration
- **Docker**: Isolated development environment

## Quality Automation Features

### Real-time Validation (DevContainer)
- **textlint Integration**: Real-time Japanese writing quality feedback
- **100-character limit**: Academic writing conciseness standard
- **Terminology consistency**: Technical term standardization
- **である調 enforcement**: Formal Japanese writing style

### Pull Request Validation (GitHub Actions)
- **HTML5 Compliance**: W3C validator integration
- **Accessibility Checks**: Alt attributes, semantic structure
- **CSS Validation**: Syntax and structure verification
- **Quality Reporting**: Detailed feedback in PR comments

## Academic Writing Standards

### Japanese Language Rules
- **Formal style**: である調 (dearu-chō) consistency
- **Sentence length**: Maximum 100 characters
- **Technical terms**: JavaScript, HTML, CSS, GitHub, LaTeX, VS Code
- **Paragraph structure**: Proper academic formatting

### HTML Quality Standards
- **Semantic markup**: Proper use of header, main, section elements
- **Accessibility**: Required alt attributes, heading hierarchy
- **Standards compliance**: HTML5 doctype, valid structure
- **Documentation**: All figures/tables referenced in text

## Ecosystem Integration

### LaTeX Thesis Environment
Part of the broader LaTeX thesis environment ecosystem:

- **latex-environment**: Provides underlying DevContainer infrastructure
- **texlive-ja-textlint**: Docker base image for textlint functionality
- **ai-academic-paper-reviewer**: AI-powered review capabilities (optional)
- **thesis-management-tools**: Administrative workflow support

### Template Relationship
```
latex-environment (DevContainer base)
    ↓
ise-report-template (HTML specialization)
    ├── HTML5/CSS focus
    ├── Web accessibility emphasis
    ├── textlint quality management
    └── GitHub workflow integration
```

## Student Workflow

### Repository Creation
1. **Template Usage**: Use as GitHub template to create personal repository
2. **Naming Convention**: `k99rs999-ise-report1` (student ID + course identifier)
3. **Privacy**: Private repository within smkwlab organization

### Development Process
1. **Branch Creation**: Working branches for each submission (`1st-draft`, `2nd-draft`)
2. **DevContainer Development**: VS Code with real-time quality feedback
3. **Server Deployment**: Upload to www-st for web accessibility
4. **Pull Request Submission**: Automated quality validation and review request

### Quality Feedback Loop
1. **Real-time**: textlint feedback during writing
2. **Pre-submission**: Local validation and preview
3. **Submission**: Automated quality report generation
4. **Review**: Faculty feedback integration
5. **Iteration**: Continuous improvement through revision cycles

## Faculty Integration

### Review Workflow
- **Automatic Assignment**: PR creation triggers review assignment
- **Quality Reports**: Automated generation of detailed quality assessments
- **Structured Feedback**: Consistent evaluation criteria
- **Progress Tracking**: Multiple draft submission support

### Administrative Features
- **PDF Generation**: Automatic PDF creation for archival
- **Quality Metrics**: Comprehensive quality reporting
- **Workflow Automation**: Minimal manual intervention required

## Technical Configuration

### textlint Configuration (Unified)
```json
{
  "rules": {
    "preset-ja-technical-writing": {
      "sentence-length": { "max": 100 },
      "no-mix-dearu-desumasu": { "preferInBody": "である" }
    },
    "terminology": {
      "terms": ["JavaScript", "HTML", "CSS", "GitHub", "LaTeX", "VS Code"]
    }
  },
  "overrides": [
    { "files": ["*.html"], "plugins": ["html"] },
    { "files": ["*.md"], "filters": ["allowlist"] },
    { "files": ["*.tex"], "plugins": ["latex2e"] }
  ]
}
```

### HTML Quality Rules (.htmlhintrc)
- Tag name lowercase enforcement
- Required alt attributes
- HTML5 doctype validation
- Unique ID requirements
- Accessibility standards compliance

## Development Guidelines

### Code Quality Standards
- Follow semantic HTML5 principles
- Maintain accessibility standards (WCAG guidelines)
- Use consistent CSS organization
- Implement responsive design principles

### Academic Content Standards
- Reference all figures and tables in text
- Maintain proper heading hierarchy (h2 → h3 → h4)
- Use one sentence per line for diff clarity
- Include meaningful alt text for images

### Workflow Standards
- Create feature branches for each draft
- Use descriptive commit messages (English)
- Test thoroughly before PR creation
- Address all automated quality feedback

## Common Use Cases

### Information Science Exercise I
- Programming exercise reports
- Algorithm analysis documentation
- Technical skill demonstration
- Structured problem-solving documentation

### Information Science Exercise II
- Team project documentation
- Collaborative development reports
- Integration project analysis
- Advanced technical implementation

## Performance Considerations

### DevContainer Optimization
- Alpine Linux base for minimal footprint
- Targeted dependency installation
- Efficient textlint configuration
- Fast startup times for student use

### CI/CD Efficiency
- Parallel validation steps
- Cached dependency management
- Selective workflow triggers
- Optimized resource usage

## Security & Privacy

### Student Data Protection
- Private repository enforcement
- Secure credential management
- No external service dependencies for core functionality
- GDPR-compliant data handling

### Quality Assurance Security
- Trusted validation tools only
- No code execution in validation
- Secure API key management
- Audit trail preservation

## Troubleshooting Guide

### Common Issues
- **textlint errors**: Check .textlintrc syntax and dependency installation
- **HTML validation failures**: Verify HTML5 structure and accessibility requirements
- **DevContainer startup**: Ensure Docker and VS Code DevContainer extension availability
- **Workflow failures**: Check .yamllint.yml compliance and GitHub Actions logs

### Performance Issues
- **Slow textlint**: Check for large files or complex regex patterns
- **CI/CD timeouts**: Review workflow complexity and resource requirements
- **Container build delays**: Verify internet connectivity and dependency availability

## Integration Notes

### Template Customization
- Maintain quality configuration integrity
- Preserve workflow automation
- Respect academic writing standards
- Ensure accessibility compliance

### Ecosystem Compatibility
- textlint configuration compatible with latex-environment standards
- HTML quality rules aligned with web accessibility best practices
- Workflow patterns consistent with thesis environment ecosystem
- Documentation standards matching organizational requirements