# Troubleshooting Guide

This document provides troubleshooting information for common issues with ise-report-template.

## Common Issues

### textlint errors
- Check .textlintrc syntax and dependency installation
- Verify Node.js compatibility and package versions
- Test with sample content to isolate rule issues

### HTML validation failures
- Verify HTML5 structure and accessibility requirements
- Check for required alt attributes on images
- Ensure proper heading hierarchy (h1 → h2 → h3)
- Validate semantic markup usage

### DevContainer startup
- Ensure Docker and VS Code DevContainer extension availability
- Check Docker daemon status and memory allocation
- Verify internet connectivity for image downloads

### Workflow failures
- Check .yamllint.yml compliance and GitHub Actions logs
- Verify workflow file syntax and permissions
- Test locally before pushing to GitHub

## Performance Issues

### Slow textlint processing
- Check for large files or complex regex patterns
- Review .textlintrc configuration for heavy rules
- Consider file exclusion patterns for non-essential content

### CI/CD timeouts
- Review workflow complexity and resource requirements
- Check for network connectivity issues
- Optimize dependency installation and caching

### Container build delays
- Verify internet connectivity and dependency availability
- Check Docker layer caching effectiveness
- Monitor base image update frequency

## Debug Commands

### textlint Testing
```bash
# Check textlint configuration
npx textlint --print-config

# Test specific files
npx textlint index.html
npx textlint *.html

# Check rule performance
npx textlint --debug index.html
```

### HTML Validation
```bash
# Local HTML5 validation
npx html5validator --root . --show-warnings

# Check specific files
npx html5validator index.html

# Accessibility testing
npx htmlhint index.html
```

### DevContainer Debug
```bash
# Check container status
docker ps

# Access container shell
docker exec -it container_name sh

# Check installed packages
npm list -g
node --version
```

### GitHub Actions Debug
```bash
# Check workflow syntax
yamllint .github/workflows/*.yml

# Local workflow testing (if act is installed)
act pull_request

# Check action logs
gh run list
gh run view <run_id>
```

## Student Workflow Issues

### Repository Creation Problems
- Verify template repository access permissions
- Check GitHub organization membership
- Ensure correct naming convention usage

### Development Environment Setup
- Confirm VS Code DevContainer extension installation
- Verify Docker Desktop is running
- Check network connectivity for container downloads

### Quality Validation Failures
- Review automated quality feedback in PR comments
- Address textlint rule violations systematically
- Validate HTML structure before submission

## Faculty Workflow Issues

### Review Assignment Problems
- Check autoassignees.yml configuration
- Verify reviewer availability and permissions
- Test with sample pull requests

### Quality Report Generation
- Verify GitHub Actions workflow permissions
- Check for API rate limit issues
- Monitor workflow execution logs

## File-specific Issues

### index.html Problems
- Validate HTML5 doctype declaration
- Check for required semantic elements
- Ensure proper alt attributes on images

### style.css Issues
- Validate CSS syntax and structure
- Check for accessibility color contrast
- Verify responsive design implementation

### Configuration File Problems
- Test .textlintrc with minimal content
- Validate .htmlhintrc rule compatibility
- Check .yamllint.yml syntax compliance