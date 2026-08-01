# AeroLM Pipeline Architecture

## Overview
The primary purpose of this repository is to ensure the versioning and integrity of all code used in architecting the data pipeline and building AI contexts. It serves as the central hub for tracking changes, collaboration, and maintaining the history of our core pipeline infrastructure.

## Scope
- **Data Pipeline Architecture:** Code, scripts, and configurations for data ingestion, processing, transformation, and storage.
- **AI Contexts:** Code, templates, and contextual data structures used for structuring data and building contexts for AI models.

## Project Structure
*(Directory structure will be updated as the project evolves)*

## Development Workflow & Best Practices

This repository uses a strict release flow to maintain the stability of the `main` branch. This flow is strictly enforced using automated GitHub Actions and Branch Protection Rules.

### Branching Strategy
- **`main`**: The production-ready state of the code. Direct pushes are disabled.
- **`develop`**: The integration branch for new features and testing.
- **`feature/*`**: Short-lived branches for developing individual features, tweaks, or bug fixes.

---

### Step-by-Step Development Process

#### 1. Clone the Repository
```bash
git clone <repository-url>
cd aerolm-pipeline-architecture
```

#### 2. Create a Feature Branch
Always branch off from `main` to keep your work up to date with the latest integrated changes. Use descriptive naming (e.g., `feature/data-ingestion`, `bugfix/context-builder`).
```bash
git switch develop
git pull origin develop
git switch -c feature/your-feature-name
```

#### 3. Make and Commit Your Changes
Make your code changes and commit them with clear, descriptive messages.
```bash
git add .
git commit -m "feat: add descriptive message about what this change does"
```

#### 4. Phase 1: Merge to Develop
Push your feature branch and open a Pull Request targeting the **`develop`** branch.
```bash
git push origin feature/your-feature-name
```
*   Have your code reviewed by team members if necessary.
*   Merge your PR into `develop`.

#### 5. Phase 2: Release to Main
Once your feature is stable in `develop` and ready for the production environment, you can open a Pull Request targeting the **`main`** branch.
*   **Automated Validation:** A GitHub Action will automatically run to verify that your feature branch has already been successfully merged into `develop`. If you try to bypass `develop`, the merge button will be blocked!
*   **Merge & Cleanup:** Once the PR is merged into `main`, a separate GitHub Action will automatically delete your feature branch on the remote repository to keep things tidy.

---

## Best Standards & Practices

### Commit Messaging
We highly recommend following the [Conventional Commits](https://www.conventionalcommits.org/) format to keep history readable:
- `feat:` for new features (e.g., `feat: add new data ingestion script`)
- `fix:` for bug fixes (e.g., `fix: resolve context timeout issue`)
- `docs:` for documentation updates
- `chore:` for maintenance tasks (e.g., updating dependencies)

### Keeping Your Local Machine Clean
Because feature branches are automatically deleted on GitHub after they are merged into `main`, your local machine will eventually hold onto "ghost" branches. Run this command occasionally to clean them up:
```bash
git fetch --prune
```

### Pull Request Etiquette
- Keep PRs small and focused on a single issue/feature.
- Provide a clear description of *why* the change is being made.
- If your change breaks existing pipeline logic, highlight it clearly in the PR description.

###before aakash test
