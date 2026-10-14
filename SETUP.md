# GitHub Profile README — Setup

## 1. Find your GitHub username
Open your GitHub profile and copy the username from the profile URL. If GitHub CLI is installed and authenticated, run:

```powershell
gh api user --jq .login
```

## 2. Create the special profile repository
1. On GitHub, create a **public** repository.
2. Set the repository name to exactly your GitHub username (for example, username `sinan-dev` means repository `sinan-dev`).
3. Initialize it with a README only if you are not planning to upload this prepared README over it.

GitHub recognizes this repository as your profile README when the repository is public and its name exactly matches your username.

## 3. Add the README
1. Open `README.md`.
2. Replace every `YOUR_GITHUB_USERNAME` with your actual username.
3. Review the projects and technology icons; remove anything you do not actively use.
4. Upload/commit `README.md` to the root of the username-named repository.

## 4. Add the contribution-snake workflow
1. In the same repository, create `.github/workflows/snake.yml`.
2. Copy the supplied `snake.yml` into it.
3. Replace `YOUR_GITHUB_USERNAME` in the workflow with your username.
4. In the repository, open **Settings → Actions → General** and ensure workflows have permission to write to the repository if your organization/repository settings require it. The workflow declares `contents: write`.
5. Open **Actions → Generate contribution snake → Run workflow**.
6. After it succeeds, the workflow creates/updates an `output` branch. The README animation image should then load. The scheduled run refreshes it daily.

## 5. Publish and check
- Visit `https://github.com/YOUR_GITHUB_USERNAME` and check the profile README.
- If the snake is missing at first, run the workflow once and allow a minute for the image to become available.
- GitHub stats cards are served by third-party services and may occasionally be rate-limited or unavailable; the README still works without them.

## Files
- `README.md` — profile README template.
- `.github/workflows/snake.yml` — daily contribution-snake workflow.
