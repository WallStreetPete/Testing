# Local setup — quick start

This repository currently contains simple static files (for example `home.html` and `about.html`). These instructions explain how to get a local copy and preview the site in a browser.

Requirements
- Git
- A web browser
- (Optional) Python 3 for a quick static file server, or Node.js if you prefer `http-server`/`live-server` tools
- (Optional) A code editor such as VS Code

1) Clone the repository

Fork the repo on GitHub (recommended), then clone your fork locally and add the upstream remote:

  git clone git@github.com:<your-username>/WallStreetPete-Testing.git
  cd WallStreetPete-Testing
  git remote add upstream git@github.com:WallStreetPete/Testing.git

Keep your main branch up to date:

  git checkout main
  git fetch upstream
  git merge upstream/main

2) Preview the files in a browser

Because this is a static site, you can open files directly in a browser, or run a local static server to avoid issues with relative paths.

Option A — open directly (quick):
- Open `home.html` or `about.html` with your browser (File > Open File...).

Option B — Python 3 static server (recommended for a local site):

  # from the repo root
  python3 -m http.server 8000

Then open http://localhost:8000/home.html in your browser.

Option C — Node.js based static server (if you have Node installed):

  # from the repo root, using npx
  npx http-server -p 8000

Or use the VS Code Live Server extension: right-click `home.html` -> "Open with Live Server".

3) Edit files
- Use your editor (VS Code, Sublime, etc.) to modify `.html` files in the repo.
- Refresh the browser to see changes (or rely on Live Server for auto-reload).

4) Tests and linting
- This repository does not include a test suite or linting configuration in the root. Follow CONTRIBUTING.md for general guidance on running tests and linters when/if they are added.

5) Contributing
- See CONTRIBUTING.md for the project's contribution workflow (fork, branch, open PR).

Troubleshooting
- If a page shows a blank screen, open the browser dev tools (Console) to check for errors or broken resource paths.
- If a local server port is already in use, change the port number (for example, `8001`).

If you want, I can expand this doc with project-specific setup steps if/when the repo adds package files (package.json, requirements.txt, etc.).