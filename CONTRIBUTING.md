# Contributing

Thanks for your interest in contributing to this project. This document explains how to set up a local development environment, create changes, and submit a clean pull request. It is intentionally generic — follow the repository README and CI config for project-specific commands.

1. Fork and clone

- Fork the repository on GitHub.
- Clone your fork and add the upstream remote:

  git clone git@github.com:<your-username>/WallStreetPete-Testing.git
  cd WallStreetPete-Testing
  git remote add upstream git@github.com:WallStreetPete/Testing.git

- Keep your main branch up to date:

  git checkout main
  git fetch upstream
  git merge upstream/main

2. Create a branch

- Create a descriptive feature branch off main:

  git checkout -b feat/short-description

3. Install dependencies (project-specific)

This repository may use different languages and package managers. Follow the README or CI for exact steps. Examples:

- Node.js (if applicable):

  npm install
  # or
  yarn install

- Python (if applicable):

  python -m venv .venv
  source .venv/bin/activate
  pip install -r requirements.txt

If the project uses another language, follow the tooling described in the README.

4. Run tests and linters

Run the project's test suite and linters before opening a PR. Examples (only if the repo uses these tools):

- npm scripts:

  npm test
  npm run lint

- pytest:

  pytest

If the repository has a CI configuration, ensure your changes satisfy the checks it runs.

5. Code style and commits

- Keep commits small and focused.
- Use clear commit messages. Example style:

  feat: add new endpoint for X
  fix: correct off-by-one in Y
  docs: update README for Z

- Run formatters/linters before committing, if the project uses them (prettier, black, eslint, etc.).

6. Tests and documentation

- Add or update tests for new behavior.
- Update README or other docs for any public-facing changes.

7. Opening a pull request

When your branch is ready:

- Push your branch to your fork: git push origin feat/short-description
- Open a pull request against the repository's main branch.
- In the PR description, include what you changed, why, and any steps to reproduce or test your changes.
- Make sure the CI checks pass and address reviewer feedback promptly.

8. Reporting issues

If you find a bug or want a feature, open an Issue with a clear title and steps to reproduce. Include environment details and relevant logs or screenshots.

9. Questions

If you're unsure about project-specific setup or conventions, open an Issue or ask a maintainer before making large changes.

Thank you for contributing! Please adapt these steps to match the project tooling and CI.
