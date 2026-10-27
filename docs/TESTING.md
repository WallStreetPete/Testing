# Testing changes locally

This document explains quick, repeatable steps to check your changes locally before opening a pull request. It focuses on this repository's static-site layout (for example `home.html`, `about.html`) but also lists general items to run if the project adds tests or linters.

## Quick pre-PR checklist

- Create a feature branch off `main` and work there.
- Run the local preview and confirm pages load as expected.
- Open browser devtools and confirm there are no console errors or broken network requests.
- Click through links, images and forms (if any) for the pages you changed.
- Run any project tests and linters (see the "Automated checks" section).
- Run formatters or pre-commit hooks if the project uses them.
- Write or update tests and docs for behavior changes.

## Preview the static site (recommended)

Option A — Python 3 static server (simple):

  # from the repo root
  python3 -m http.server 8000 --bind 127.0.0.1

Then open http://localhost:8000/home.html (or the page you changed) in your browser.

Option B — Node-based static server (if you have Node):

  # from the repo root
  npx http-server -p 8000

Option C — VS Code Live Server:
- Install the Live Server extension, open the repo, right-click `home.html` -> "Open with Live Server".

If the server port is busy, change the port (for example, `8001`).

## What to check manually

- Does the page render without missing assets (images, CSS, JS)?
- Are internal links working? (navigate between pages you edited)
- Any JavaScript console errors or network 404/500 responses?
- Layout and responsive checks: resize the browser or use devtools device toolbar.
- Accessibility smoke check: keyboard navigation, alt text on images, color contrast where applicable.

Tip: Open the browser DevTools Network and Console panels while exercising each page.

## Automated checks (if the repo adds them)

Run project tests and linters before committing. Examples (only if present):

- npm scripts:

  npm install
  npm test
  npm run lint

- Python (if a test suite exists):

  python -m venv .venv
  source .venv/bin/activate
  pip install -r requirements.txt
  pytest

If the project later adds a GitHub Actions workflow, ensure your local runs satisfy the same checks.

Optional: use `act` to run GitHub Actions locally if you want to reproduce CI behavior (requires installing `act`).

## Optional link checking and validation

- Run an HTML validator or a link checker (for example, `linkinator` or other tools) if links are important:

  npx linkinator http://localhost:8000

- For HTML validation, consider online validators or CLI tools.

## Commit and PR checklist

- Keep commits small and focused; use a descriptive branch name.
- Run formatters/linters before commit.
- Push your branch and open a PR against `main`.
- In the PR description, include what you changed, why, and steps to reproduce locally.
- Ensure CI checks pass and address review feedback.

## Troubleshooting

- Blank page or missing assets: open the browser DevTools Console and Network panels to inspect JavaScript errors, 404s, or other failed resource loads.
- Relative paths broken: prefer running a local server (see the "Preview the static site" section) instead of opening files directly via file://.
- Server not reachable or you want to limit exposure: bind the Python server to localhost (example: `python3 -m http.server 8000 --bind 127.0.0.1`) or verify the server address.
- Port in use: change the server port (for example, 8001) or stop the process using the port (tools: lsof/netstat).
- Tests or linters failing locally: run them with verbose output and confirm dependencies (package.json / requirements.txt) match the environment.


---

If you'd like, I can add repo-specific test and linter commands to this doc when package files (package.json, requirements.txt, etc.) appear in the repo.