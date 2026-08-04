# Deploy the profile

This folder is ready to become the special GitHub profile repository for
[`7amankrishna`](https://github.com/7amankrishna).

## 1. Create the profile repository

Create a **public** repository named exactly:

```text
7amankrishna
```

Copy these items to its root:

```text
README.md
assets/
.github/
```

## 2. Enable generated visuals

In the profile repository, open:

```text
Settings → Actions → General → Workflow permissions
```

Select **Read and write permissions**, save, then run **Refresh profile assets**
from the Actions tab. The workflow refreshes:

- `assets/github-metrics.svg`
- the `output` branch containing the light and dark contribution snakes
- `profile-3d-contrib/` containing the 3D contribution calendar

For richer private-contribution metrics, create a classic personal access token
with `repo` and `read:user` scopes and save it as the repository secret
`METRICS_TOKEN`. Public metrics work with the default GitHub token.

## 3. Review personal links

The profile uses the confirmed GitHub handle, portfolio, email, and Instagram
links available in the source project. Before publishing, confirm these
convention-based URLs:

- `https://www.linkedin.com/in/7amankrishna/`
- `https://x.com/7amankrishna`
- `https://amankrishna.in/#resume`

No token, API key, or secret belongs in `README.md`.

## 4. Replace the username later

If the GitHub username changes, replace every exact instance of
`7amankrishna` in:

- `README.md`
- `.github/workflows/profile-assets.yml`

Also rename the special profile repository to match the new username.
