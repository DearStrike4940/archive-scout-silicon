# GitHub setup

## Upload correctly

The repository root must directly contain `.github`, `archive_scout`, `docs`, `examples`, `scripts`, `tests`, `README.md`, `requirements-build.txt`, and `run_app.py`. Do not put them inside an extra nested folder.

If using Finder or another file manager, hidden folders may not be visible. Use Git whenever possible:

```bash
cd path/to/archive-scout-apple-silicon
git init
git add .
git commit -m "Initial Archive Scout for Apple Silicon release"
git branch -M main
git remote add origin https://github.com/YOUR_GITHUB_USERNAME/archive-scout-apple-silicon.git
git push -u origin main
```

## Repository settings

Open **Settings → Actions → General**. Select **Allow all actions and reusable workflows**. Under Workflow permissions, select **Read and write permissions**, then save.

## Manual test build

Open **Actions → Build Apple Silicon macOS App → Run workflow**. Select `main` and run it. After it succeeds, download the artifact named `ArchiveScout-macOS-Apple-Silicon` from the workflow summary.

## Publish a release

Create a GitHub release with a tag such as `v1.2.0`, or push that tag from Git. The workflow runs again and uploads:

- `ArchiveScout-macOS-Apple-Silicon.dmg`
- `ArchiveScout-macOS-Apple-Silicon.dmg.sha256`

The permanent latest-download link is:

```text
https://github.com/YOUR_GITHUB_USERNAME/archive-scout-apple-silicon/releases/latest/download/ArchiveScout-macOS-Apple-Silicon.dmg
```

Keep the release filename unchanged so the permanent link continues to work.
