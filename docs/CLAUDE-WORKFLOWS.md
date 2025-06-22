# Workflows and Usage Examples

This document covers student and faculty workflows for ise-report-template.

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

## Development Examples

### Basic Report Structure
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

### Quality Rules Application
```bash
# Real-time quality checking during development
npx textlint index.html

# Specific rule checking
npx textlint --rule sentence-length index.html
npx textlint --rule terminology index.html

# Auto-fix common issues
npx textlint --fix index.html
```

### Accessibility Implementation
```html
<!-- Good example: Proper semantic structure -->
<section>
    <h2>実験手順</h2>
    <ol>
        <li>HTMLファイルを作成する。</li>
        <li>CSSファイルを作成し、スタイルを定義する。</li>
        <li>ブラウザで表示を確認する。</li>
    </ol>
    
    <figure>
        <img src="procedure.png" alt="実験手順を示すフローチャート">
        <figcaption>図2: 実験手順のフローチャート</figcaption>
    </figure>
</section>
```

## Branch Management Examples

### Draft Workflow
```bash
# Create working branch
git checkout -b 1st-draft

# Development cycle
# ... edit index.html, style.css ...
git add .
git commit -m "Add experiment overview section"

# Quality validation
npx textlint index.html
npx html5validator index.html

# Push and create PR
git push -u origin 1st-draft
gh pr create --title "第1稿提出" --body "実験概要と結果を記述しました。"
```

### Revision Workflow
```bash
# Address review feedback
git checkout 1st-draft

# Make improvements
# ... address textlint and review comments ...
git add .
git commit -m "Fix textlint issues and improve accessibility"

# Push updates
git push origin 1st-draft
# PR automatically updated
```

### Final Submission
```bash
# Create final draft
git checkout -b final-submission
git merge 1st-draft

# Final quality check
npx textlint index.html
npx html5validator index.html
npx htmlhint index.html

# Submit final version
git push -u origin final-submission
gh pr create --title "最終提出" --body "全ての指摘事項を修正し、最終版として提出します。"
```

## Quality Validation Examples

### textlint Configuration Testing
```bash
# Test sentence length rule
echo "これは100文字を超える非常に長い文章でありテストのために意図的に作成されたものでありアカデミックライティングの基準に適合しない例である。" | npx textlint --stdin

# Test terminology consistency
echo "JavaScriptとjavaScriptが混在している。" | npx textlint --stdin --rule terminology
```

### HTML Validation Workflow
```bash
# Comprehensive validation
npx html5validator --root . --show-warnings --format json

# Accessibility-focused validation
npx htmlhint --config .htmlhintrc index.html

# CSS validation
npx stylelint style.css
```

## GitHub Actions Integration

### Automated Quality Reports
The template automatically generates quality reports on pull request creation:

1. **HTML5 Validation**: W3C compliance checking
2. **Accessibility Audit**: Alt attributes, semantic structure
3. **textlint Analysis**: Japanese writing quality assessment
4. **CSS Validation**: Syntax and structure verification

### Review Assignment
```yaml
# .github/workflows/autoassignees.yml example
name: Auto-assign reviewers
on:
  pull_request:
    types: [opened]
jobs:
  assign:
    runs-on: ubuntu-latest
    steps:
      - uses: kentaro-m/auto-assign-action@v1.2.5
        with:
          configuration-path: .github/auto_assign.yml
```

## Server Deployment

### www-st Upload
```bash
# Example deployment script
#!/bin/bash
scp -r *.html *.css *.png user@www-st.cse.kyusan-u.ac.jp:~/public_html/ise-report/

# Verify deployment
curl -I https://www-st.cse.kyusan-u.ac.jp/~user/ise-report/
```

## Integration with Ecosystem

### Template Relationship
- Uses latex-environment DevContainer infrastructure
- Inherits textlint configuration standards
- Follows thesis environment quality practices
- Integrates with GitHub-based review workflows

### Quality Standards Alignment
- Consistent with latex-environment textlint rules
- Compatible with thesis management workflows
- Aligned with academic writing standards
- Supports faculty review processes