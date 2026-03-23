<div align="center">

# 🙌 Contributing to dynamicdev-official
</div>

<div align="center">

[![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=for-the-badge)](https://github.com/dynamicdev-official)
[![GitHub](https://img.shields.io/badge/GitHub-dynamicdev--official-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/dynamicdev-official)
[![Code of Conduct](https://img.shields.io/badge/Code_of_Conduct-v2.1-FF6B6B?style=for-the-badge)](CODE_OF_CONDUCT.md)

**Thank you for considering to contribute to dynamicdev-official projects!**

We welcome contributions from developers of all levels — from fixing typos to building new features.

</div>

---

## 📋 Table of Contents

- [Code of Conduct](#-code-of-conduct)
- [Getting Started](#-getting-started)
- [Development Setup](#-development-setup)
- [Making Changes](#-making-changes)
- [Commit Guidelines](#-commit-guidelines)
- [Pull Request Process](#-pull-request-process)
- [Coding Standards](#-coding-standards)
- [Testing](#-testing)
- [Documentation](#-documentation)
- [Release Process](#-release-process)
- [Community](#-community)
- [License](#-license)

---

## 🤝 Code of Conduct

### Our Pledge

We are committed to providing a welcoming and inspiring community for all.

### Our Standards

Examples of behavior that contributes to creating a positive environment:

- **Using welcoming and inclusive language**
- **Being respectful of differing opinions, viewpoints, and experiences**
- **Gracefully accepting constructive criticism**
- **Focusing on what is best for the community**
- **Showing empathy towards other community members**

Examples of unacceptable behavior:

- **The use of sexualized language or imagery**
- **Trolling, insulting/derogatory comments, and personal or political attacks**
- **Public or private harassment**
- **Publishing others' private information without explicit permission**
- **Other conduct which could reasonably be considered inappropriate in a professional setting**

### Enforcement

Project maintainers are responsible for clarifying standards of acceptable behavior and are expected to take appropriate and fair corrective action.

Contact: support@dynamicdev.asia

---

## 🚀 Getting Started

### Prerequisites

- **Git**: Version control
- **Python 3.9+**: Core development language
- **Docker**: Container support (optional but recommended)
- **Node.js 18+**: For frontend projects (if applicable)

### Quick Start

1. **Fork the repository**
   ```bash
   # Go to https://github.com/dynamicdev-official/<project>
   # Click "Fork" button
   ```

2. **Clone your fork**
   ```bash
   git clone https://github.com/YOUR_USERNAME/<project>.git
   cd <project>
   ```

3. **Add upstream remote**
   ```bash
   git remote add upstream https://github.com/dynamicdev-official/<project>.git
   git remote -v  # Verify
   ```

4. **Create feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

---

## 🛠️ Development Setup

### Local Development Environment

#### Python Projects

```bash
# Create virtual environment
python -m venv venv

# Activate venv
# On Linux/Mac:
source venv/bin/activate
# On Windows:
venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
pip install -r requirements-dev.txt  # Development tools

# Install pre-commit hooks
pre-commit install
```

#### With Docker

```bash
# Build development image
docker build -t project-dev -f Dockerfile.dev .

# Run container
docker run -it -v $(pwd):/app project-dev /bin/bash
```

### IDE Setup (Recommended)

#### VS Code
```bash
# Install extensions:
- Python (ms-python.python)
- Pylance (ms-python.vscode-pylance)
- Black Formatter (ms-python.black-formatter)
- Flake8 (ms-python.flake8)
- pytest (littlefoxteam.vscode-python-test-adapter)

# .vscode/settings.json
{
  "python.linting.enabled": true,
  "python.linting.flake8Enabled": true,
  "python.formatting.provider": "black",
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "ms-python.black-formatter"
}
```

#### PyCharm
```bash
# Recommended settings:
- Enable Code Inspections
- Set up Python Interpreter from venv
- Enable Git integration
- Configure Run/Debug configurations
```

---

## ✍️ Making Changes

### Branch Naming Convention

```
feature/add-webhook-support          # New feature
bugfix/fix-memory-leak              # Bug fix
docs/update-readme                  # Documentation
refactor/optimize-database-query    # Code refactoring
chore/upgrade-dependencies          # Maintenance
hotfix/security-patch               # Urgent fix
```

### Commit Strategy

Keep commits atomic and focused:

```bash
# Good: Single responsibility
git commit -m "feat: add webhook retry logic"

# Bad: Multiple unrelated changes
git commit -m "add webhook retry and fix UI bug and update docs"
```

### Keeping Fork Updated

```bash
# Fetch latest changes
git fetch upstream

# Rebase your branch
git rebase upstream/main

# Or merge (less clean but safer)
git merge upstream/main
```

---

## 📝 Commit Guidelines

### Commit Message Format

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Type

- **feat**: A new feature
- **fix**: A bug fix
- **docs**: Documentation only changes
- **style**: Changes that don't affect code meaning (formatting, missing semicolons, etc)
- **refactor**: Code change that neither fixes a bug nor adds a feature
- **perf**: Code change that improves performance
- **test**: Adding missing tests or correcting existing tests
- **chore**: Changes to build process, dependencies, or tooling
- **ci**: Changes to CI configuration files and scripts

### Scope

The scope should specify what part of the codebase is affected:

```
feat(api): add rate limiting middleware
fix(dashboard): resolve null pointer exception
docs(readme): update installation instructions
```

### Subject

- Use imperative mood ("add" not "added" or "adds")
- Don't capitalize first letter
- No period at the end
- Limit to 50 characters

### Body

- Explain **what** and **why**, not **how**
- Wrap at 72 characters
- Separate from subject with blank line
- Use bullet points for multiple changes

```
feat(webhook): implement automatic retry mechanism

- Add exponential backoff algorithm
- Configure max retries via environment variable
- Add comprehensive logging for debugging
- Improve reliability for intermittent failures
```

### Footer

Reference issues and breaking changes:

```
Fixes #123
Closes #456
BREAKING CHANGE: webhook format changed from v1 to v2
```

### Examples

**Good commit:**
```
feat(auth): add SAML authentication support

Implement SAML 2.0 protocol support for enterprise users.
Includes:
- SAML metadata parsing
- Assertion verification
- User provisioning
- Session management

Allows users to authenticate using their corporate identity provider.

Fixes #789
```

**Bad commit:**
```
update stuff
```

---

## 🔀 Pull Request Process

### Pre-PR Checklist

```bash
# Run tests
pytest -v

# Check code quality
flake8 .
black --check .
pylint src/

# Check types (if using)
mypy .

# Build documentation
cd docs && make html

# Run security checks
bandit -r src/
safety check
```

### Create Pull Request

1. **Ensure base branch is up-to-date**
   ```bash
   git fetch upstream
   git rebase upstream/main
   ```

2. **Push to your fork**
   ```bash
   git push origin feature/your-feature-name
   ```

3. **Create PR on GitHub**
   - Title: Follow commit message format
   - Description: Use template below

### PR Description Template

```markdown
## Description

Brief explanation of changes. What problem does this solve?

## Type of Change

- [ ] New feature
- [ ] Bug fix
- [ ] Documentation update
- [ ] Performance improvement
- [ ] Code refactoring
- [ ] Breaking change

## Related Issues

Fixes #123

## Changes Made

- Change 1
- Change 2
- Change 3

## Testing

- [ ] Unit tests added/updated
- [ ] Integration tests passed
- [ ] Manual testing completed

Describe how to test your changes:

```bash
pytest -v
```

## Screenshots (if applicable)

Before & After screenshots for UI changes

## Checklist

- [ ] Code follows style guidelines
- [ ] Self-review completed
- [ ] Comments added for complex logic
- [ ] Documentation updated
- [ ] No breaking changes introduced
- [ ] All tests passing
- [ ] No new warnings generated

## Performance Impact

Does this affect performance?
- [ ] No
- [ ] Minor impact
- [ ] Significant impact

Describe: ...

## Breaking Changes

Any breaking changes?
- [ ] No
- [ ] Yes

Describe migration path: ...
```

### PR Review Process

1. **Automatic checks run**
   - Linting
   - Tests
   - Code coverage
   - Security scans

2. **Code review by maintainers**
   - Functionality
   - Code quality
   - Documentation
   - Performance

3. **Address feedback**
   ```bash
   # Make changes
   git add .
   git commit -m "refactor: address code review feedback"
   git push origin feature/your-feature-name
   ```

4. **Approval & Merge**
   - Minimum 1 approval required
   - All checks must pass
   - Maintainer merges with squash

---

## 🎯 Coding Standards

### Python Style Guide (PEP 8 + Enhancement)

```python
# Good: Clear, readable, well-documented
def process_webhook_payload(payload: dict) -> WebhookResult:
    """
    Process incoming webhook payload.
    
    Args:
        payload: Webhook data from external service
        
    Returns:
        WebhookResult with status and processed data
        
    Raises:
        ValidationError: If payload format is invalid
        TimeoutError: If processing takes too long
    """
    # Validate payload
    if not payload or not isinstance(payload, dict):
        raise ValidationError("Payload must be non-empty dict")
    
    # Process with error handling
    try:
        result = validate_and_process(payload)
        return WebhookResult(status="success", data=result)
    except Exception as e:
        logger.error(f"Webhook processing failed: {e}")
        raise


# Bad: Unclear, no documentation
def process(p):
    if p:
        return validate(p)
    return None
```

### Code Quality Tools

Auto-format on save:

```bash
# Install tools
pip install black flake8 pylint mypy

# Format code
black .

# Lint
flake8 .

# Type check
mypy .

# Code complexity
pylint src/

# Security
bandit -r src/
```

### Naming Conventions

```python
# Classes: PascalCase
class WebhookController:
    pass

# Functions/Methods: snake_case
def process_webhook():
    pass

# Constants: UPPER_SNAKE_CASE
MAX_RETRIES = 3
DEFAULT_TIMEOUT = 30

# Private: _leading_underscore
_internal_helper_function()

# Protected: _leading_underscore (Python convention)
self._protected_method()

# Magic methods: __double_underscore__
def __init__(self):
    pass
```

### Docstring Standard

```python
def fetch_webhook_data(
    url: str,
    timeout: int = 30,
    retries: int = 3
) -> dict:
    """
    Fetch webhook data from remote endpoint.
    
    This function handles retries with exponential backoff
    and proper error logging.
    
    Args:
        url: The webhook endpoint URL
        timeout: Request timeout in seconds (default: 30)
        retries: Number of retry attempts (default: 3)
        
    Returns:
        Dictionary containing webhook data
        
    Raises:
        ConnectionError: If all retry attempts fail
        TimeoutError: If request exceeds timeout
        
    Example:
        >>> data = fetch_webhook_data("https://example.com/webhook")
        >>> print(data['status'])
        'success'
    """
    pass
```

### Import Order

```python
# 1. Standard library
import os
import sys
from typing import Optional, Dict

# 2. Third-party
import requests
from fastapi import FastAPI
import numpy as np

# 3. Local application
from app.models import Webhook
from app.utils import logger
```

---

## 🧪 Testing

### Test Structure

```
tests/
├── unit/
│   ├── test_models.py
│   ├── test_utils.py
│   └── test_services.py
├── integration/
│   ├── test_api.py
│   └── test_database.py
├── e2e/
│   └── test_workflows.py
└── fixtures/
    ├── mock_data.py
    └── sample_payloads.json
```

### Writing Tests

```python
import pytest
from app.webhook import process_webhook


class TestWebhookProcessing:
    """Test suite for webhook processing."""
    
    @pytest.fixture
    def sample_payload(self):
        """Provide sample webhook payload."""
        return {
            "event": "message.created",
            "data": {"text": "Hello, World!"}
        }
    
    def test_process_valid_payload(self, sample_payload):
        """Test processing valid webhook payload."""
        result = process_webhook(sample_payload)
        assert result.status == "success"
        assert result.data["text"] == "Hello, World!"
    
    def test_process_invalid_payload(self):
        """Test processing invalid webhook payload."""
        with pytest.raises(ValidationError):
            process_webhook({"invalid": "payload"})
    
    def test_process_timeout(self, mocker):
        """Test processing timeout handling."""
        mocker.patch(
            "app.webhook.fetch_data",
            side_effect=TimeoutError()
        )
        with pytest.raises(TimeoutError):
            process_webhook({"url": "https://example.com"})
    
    @pytest.mark.parametrize(
        "payload,expected",
        [
            ({"event": "created"}, "success"),
            ({"event": "updated"}, "success"),
            ({"event": "deleted"}, "success"),
        ]
    )
    def test_all_event_types(self, payload, expected):
        """Test all event types."""
        result = process_webhook(payload)
        assert result.status == expected
```

### Running Tests

```bash
# Run all tests
pytest -v

# Run specific test
pytest tests/unit/test_webhook.py::TestWebhookProcessing::test_process_valid_payload

# Run with coverage
pytest --cov=src --cov-report=html

# Run in parallel
pytest -n auto

# Run with markers
pytest -m "not slow"
```

### Coverage Requirements

```bash
# Minimum 80% coverage
pytest --cov=src --cov-fail-under=80

# Generate report
pytest --cov=src --cov-report=html
# Open htmlcov/index.html in browser
```

---

## 📚 Documentation

### Code Comments

```python
# Good: Explains WHY, not WHAT
def calculate_exponential_backoff(attempt: int) -> float:
    # Base delay starts at 1s, doubles on each retry
    # Capped at 60s to prevent excessive delays
    base_delay = min(2 ** attempt, 60)
    # Add random jitter (±20%) to prevent thundering herd
    jitter = base_delay * random.uniform(0.8, 1.2)
    return jitter


# Bad: Restates obvious code
def calculate_exponential_backoff(attempt: int) -> float:
    # Calculate 2 to the power of attempt
    base_delay = 2 ** attempt
    # Return it
    return base_delay
```

### Documentation Updates

```markdown
# Update docs/ARCHITECTURE.md with diagrams
# Update docs/API.md with new endpoints
# Update docs/SETUP.md for new dependencies
# Add CHANGELOG.md entry
```

---

## 🔄 Release Process

### Version Numbering (Semantic Versioning)

```
MAJOR.MINOR.PATCH

- MAJOR: Breaking changes
- MINOR: New features (backward compatible)
- PATCH: Bug fixes
```

### Release Checklist

```bash
# 1. Update version
# Update __version__ in __init__.py
# Update version in pyproject.toml

# 2. Update changelog
# docs/CHANGELOG.md

# 3. Create release branch
git checkout -b release/v1.2.0

# 4. Run full test suite
pytest --cov=src --cov-fail-under=80
docker build -t project:v1.2.0 .

# 5. Create PR for release
# Title: "Release v1.2.0"

# 6. Merge to main
git checkout main
git pull origin main
git merge --no-ff release/v1.2.0

# 7. Tag release
git tag -a v1.2.0 -m "Release version 1.2.0"
git push origin main
git push origin v1.2.0

# 8. Delete release branch
git branch -d release/v1.2.0
```

---

## 👥 Community

### Getting Help

- **Discord**: [Community Server](#) (coming soon)
- **Email**: support@dynamicdev.asia
- **Issues**: Use GitHub Issues with labels

### Reporting Bugs

1. **Search existing issues** first
2. **Use bug report template**
3. **Include minimal reproduction case**
4. **Provide environment details**

```markdown
## Description
Brief description of the bug

## Expected Behavior
What should happen

## Actual Behavior
What actually happens

## Steps to Reproduce
1. Step 1
2. Step 2
3. Step 3

## Environment
- OS: Windows 10
- Python: 3.9.1
- Python version: (output of `python --version`)
```

### Feature Requests

1. **Check for duplicates**
2. **Use feature request template**
3. **Explain use case clearly**

```markdown
## Use Case
Why do you need this feature?

## Proposed Solution
How should it work?

## Alternatives Considered
Other approaches?
```

---

## 📄 License

By contributing to this project, you agree that your contributions will be licensed under its MIT License.

---

## 🎉 Recognition

Contributors will be recognized in:

- **CONTRIBUTORS.md** file
- **Release notes** for major contributions
- **Project website** (if applicable)
- **GitHub contributors** page

### Hall of Fame Tiers

- 🥇 **Gold**: 50+ contributions
- 🥈 **Silver**: 20-49 contributions
- 🥉 **Bronze**: 5-19 contributions
- ⭐ **Contributor**: 1-4 contributions

---

<div align="center">

## 🚀 Ready to Contribute?

1. [Fork the repo](#getting-started)
2. [Set up development environment](#development-setup)
3. [Create a feature branch](#making-changes)
4. [Submit a pull request](#pull-request-process)

**Questions?** Open an issue or email support@dynamicdev.asia

**Thank you for making dynamicdev_ better!** 💜

---

[![GitHub](https://img.shields.io/badge/GitHub-dynamicdev--official-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/dynamicdev-official)
[![Twitter](https://img.shields.io/badge/Twitter-@dynamicdev_-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](#)
[![Email](https://img.shields.io/badge/Email-support%40dynamicdev.asia-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:support@dynamicdev.asia)

</div>
