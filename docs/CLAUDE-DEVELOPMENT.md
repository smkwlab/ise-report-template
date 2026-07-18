# Development Guide

This document covers the development workflow, architecture, and technical details for ise-report-template.

The student-facing submission flow (0th-draft → PR → auto-created next
draft → `final` tag) is documented in the [README](../README.md) and is not
duplicated here.

## Key Technologies

### Quality Management Stack
- **textlint**: Japanese academic writing validation (runs in the DevContainer and in CI)
- **html5validator / htmlhint**: W3C HTML5 compliance and accessibility validation (run in CI via the org-standard reusable workflow)
- **yamllint**: Workflow configuration validation (`.yamllint.yml`)

### Development Environment
- **DevContainer**: textlint container (see `.devcontainer/Dockerfile`); textlint is the only tool installed locally
- **VS Code Extensions**: Live Server, textlint, GitHub Pull Request integration
- **Docker**: Isolated development environment

## GitHub Actions Workflows

All seven workflows are thin callers of the org-standard reusable workflows
in `smkwlab/.github` (`@v1`), which centrally pins tool versions:

| Workflow | Trigger | Purpose |
|---|---|---|
| `html-validation.yml` | PR touching `*.html` / `*.css` | W3C + accessibility validation, report in PR |
| `create-next-draft.yml` | PR opened | Auto-create the next draft branch |
| `sync-next-draft.yml` | push to draft branches | Merge applied suggestions into the next draft |
| `prevent-draft-merge.yml` | PR | Block accidental merges of draft PRs |
| `ai-paper-review.yml` | PR | AI-based review comments |
| `claude-qa.yml` | issue/PR comment | @claude Q&A for students |
| `notify-ml-on-pr.yml` | PR | Notify the lab ML |

There is no tag-triggered workflow: the `final` tag is a submission marker
(README「完成・提出」), not an automation trigger. There is also no PDF
generation and no reviewer auto-assignment workflow in this template.

## Quality Automation Features

### Real-time Validation (DevContainer)
- **textlint Integration**: Real-time Japanese writing quality feedback
- **100-character limit**: Academic writing conciseness standard
- **である調 enforcement**: Formal Japanese writing style

### Pull Request Validation (GitHub Actions)
- **HTML5 Compliance**: W3C validator integration
- **Accessibility Checks**: Alt attributes, semantic structure
- **Quality Reporting**: Detailed feedback in PR comments

## Academic Writing Standards

### Japanese Language Rules
The authoritative configuration is [`.textlintrc`](../.textlintrc) — do not
restate it here; key rules as of this writing:

- **Formal style**: である調 (via `preset-ja-technical-writing`)
- **Sentence length**: max 100 characters (URLs/email links skipped)
- **Kanji runs**: max 8 continuous kanji, with an allowlist for institution names
- **Plugins**: `html` and `latex2e` (the config is shared with the LaTeX templates), comments filter enabled

### HTML Quality Standards
- **Semantic markup**: Proper use of header, main, section elements
- **Accessibility**: Required alt attributes, heading hierarchy
- **Standards compliance**: HTML5 doctype, valid structure (rules in [`.htmlhintrc`](../.htmlhintrc))
- **Documentation**: All figures/tables referenced in text

### Report Structure Example
```html
<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>情報科学演習レポート</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>情報科学演習 I レポート</h1>
        <p>学籍番号: k21rs001 氏名: 山田太郎</p>
    </header>

    <main>
        <section>
            <h2>実験概要</h2>
            <p>本実験では、HTMLとCSSを用いてWebページを作成した。</p>
        </section>

        <section>
            <h2>実験結果</h2>
            <figure>
                <img src="result.png" alt="実験結果のスクリーンショット">
                <figcaption>図1: 作成したWebページの表示結果</figcaption>
            </figure>
        </section>

        <section>
            <h2>考察</h2>
            <p>図1に示すように、適切なHTMLとCSSの使用により、見やすいWebページが作成できた。</p>
        </section>
    </main>
</body>
</html>
```

## Testing Guidelines

### Local (DevContainer)
Only textlint is available locally:

```bash
# Check files
npx textlint index.html

# Auto-fix fixable issues (use with care)
npx textlint --fix index.html

# Inspect the effective configuration
npx textlint --print-config
```

### CI
HTML validation (html5validator / htmlhint) runs in the
`html-validation.yml@v1` reusable workflow on every PR that touches
`*.html` / `*.css`; results appear in the PR. To run html5validator
locally, install it separately (`pip install html5validator`) — it is a
Python tool and is not part of the DevContainer.

### Workflow configuration
```bash
yamllint -c .yamllint.yml .github/workflows/
```

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
- Draft branches come from the automation: `0th-draft` exists at repository
  creation, and each PR auto-creates the next draft branch (do not create
  draft branches by hand)
- Use descriptive commit messages (English)
- Address all automated quality feedback before requesting review

## Ecosystem Integration

### Related Repositories
- **latex-environment**: Provides the DevContainer pattern this template follows
- **texlive-ja-textlint**: Docker base image for textlint functionality
- **smkwlab/.github**: Org-standard reusable workflows called by this repo's workflows; versions pinned centrally
- **student-repo-management**: Repository creation (`DOC_TYPE=ise`) and registration

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

## Security & Privacy

- Student repositories are private within the organization
- Validation runs no student-supplied code (static checking only)
- No external service dependencies for core functionality

## Integration Notes

### Template Customization
- Maintain quality configuration integrity (`.textlintrc`, `.htmlhintrc`)
- Preserve workflow automation
- Respect academic writing standards
- Ensure accessibility compliance

### Ecosystem Compatibility
- textlint configuration compatible with latex-environment standards
- HTML quality rules aligned with web accessibility best practices
- Workflow patterns consistent with the thesis environment ecosystem
