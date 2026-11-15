# Independent dictionary ZIP mirror

Forks copy Git commits, not binary release assets. The original project's release v1.3.0 contains 74 ZIP files (approximately 814 MB), while this fork initially has no releases.

## Run once

1. Merge the PR containing `.github/workflows/mirror-upstream-release.yml`.
2. Enable GitHub Actions for this fork if prompted.
3. Go to Actions > Mirror dictionary ZIP files > Run workflow and keep tag `v1.3.0`.
4. Wait for a successful run: it checks the ZIP count, publishes the files and SHA256SUMS in a GitHub Release, and only then changes README and website download URLs to this fork.
5. Verify https://github.com/danilfg/koreader-dicts/releases/latest/download/en-ru.zip and https://github.com/danilfg/koreader-dicts/releases/latest/download/ru-en.zip.

If the run fails before publication, README links are left untouched. A partially uploaded release might remain in draft; rerunning is supported. If the branch is protected, the final automated README update may fail after mirroring; update links in a PR instead.

GitHub Actions commits using GITHUB_TOKEN do not normally trigger Pages deployment. If using your own GitHub Pages website, manually rerun `pages.yml` after completion.

Individual dictionary ZIPs include LICENSE and ATTRIBUTION. Check and retain attribution for each pair; licenses are not identical.

Finally change the Chrome extension's default dictionary download host to danilfg only after confirming files exist.
