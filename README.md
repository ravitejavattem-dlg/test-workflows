# Test Workflows

This repository demonstrates a GitHub Actions workflow for automatically tagging the `main` branch when a feature branch is merged.

## Workflow Overview

- **Workflow File:** [.github/workflows/tag-main-with-feature.yml](.github/workflows/tag-main-with-feature.yml)
- **Trigger:** When a pull request targeting `main` is closed and merged, and the source branch name starts with `feature/v`.
- **Action:** 
  - Extracts the version number from the feature branch name (e.g., `feature/v1.2.3`).
  - Checks out the `main` branch.
  - Checks if a tag for that version already exists.
  - If not, creates and pushes a new tag (e.g., `v1.2.3`) to the repository.

## Branch Naming Convention

Feature branches should be named using the pattern:  
`feature/v<major>.<minor>.<patch>`  
Example: `feature/v1.2.3`

## How It Works

1. When a pull request from a branch like `feature/v1.2.3` is merged into `main`, the workflow runs.
2. The workflow extracts the version number from the branch name.
3. If a tag `v1.2.3` does not already exist, it creates and pushes the tag to the repository.

## Files

- [.github/workflows/tag-main-with-feature.yml](.github/workflows/tag-main-with-feature.yml): GitHub Actions workflow definition.
- [.gitignore](.gitignore): Standard Node.js and tool-specific ignores.

## License

This project is for demonstration purpose.