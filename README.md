# Style Guide

## Overview

Shared code style configurations and linting rules for Python, Ruby, and TypeScript/JavaScript projects.
Used as a git submodule across multiple repositories to maintain consistent code formatting and quality standards.

### Tech stack

| Category | Technologies                      |
| -------- | --------------------------------- |
| Python   | Ruff, Flake8 (legacy)             |
| Ruby     | RuboCop                           |
| TypeScript/JavaScript | Biome                |

## Usage as submodule

### Adding to a project

```sh
# Add as submodule
git submodule add git@github.com:bloomon/style-guide style-guide

# Initialize and update
git submodule update --init --recursive
```

### Using configurations

**Python (Ruff)**
```sh
# In pyproject.toml
[tool.ruff]
extend = "style-guide/python/ruff.toml"
```

**Python (Flake8 - legacy)**
```sh
# In setup.cfg or tox.ini
[flake8]
extend-config = style-guide/python/flake8
```

**Ruby (RuboCop)**
```sh
# In .rubocop.yml
inherit_from: style-guide/ruby/rubocop.yml
```

**TypeScript/JavaScript (Biome)**
```sh
# In biome.json
{
  "extends": ["./style-guide/typescript/biome.json"]
}
```

### Updating submodule

```sh
# Update to latest version
git submodule update --remote style-guide

# Commit the update
git add style-guide
git commit -m "Update style-guide submodule"
```