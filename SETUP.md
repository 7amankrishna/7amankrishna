# Publish this profile dashboard

GitHub displays a profile README only from a public repository with the exact same name as the account: `7amankrishna/7amankrishna`.

## 1. Create the profile repository

On GitHub, create a **public** repository named `7amankrishna`. Do not initialize it with a README, license, or `.gitignore`.

## 2. Publish these files

Run the following from this workspace in PowerShell:

```powershell
git clone https://github.com/7amankrishna/7amankrishna.git
Copy-Item -Path .\github-profile-dashboard\README.md -Destination .\7amankrishna\README.md -Force
New-Item -ItemType Directory -Force -Path .\7amankrishna\.github\workflows | Out-Null
Copy-Item -Path .\github-profile-dashboard\.github\workflows\metrics.yml -Destination .\7amankrishna\.github\workflows\metrics.yml -Force
Set-Location .\7amankrishna
git add README.md .github\workflows\metrics.yml
git commit -m "Create professional GitHub profile dashboard"
git push -u origin main
```

If Git asks you to authenticate, sign in with the GitHub account that owns `7amankrishna`.

## 3. Enable private-activity metrics (optional)

1. On GitHub, go to **Settings → Developer settings → Personal access tokens → Fine-grained tokens**.
2. Create a token named `profile-metrics`, restricted to the `7amankrishna` profile repository.
3. Give it **Contents: Read and write** and **Metadata: Read** repository permissions. Keep access restricted to only the profile repository.
4. In the `7amankrishna` repository go to **Settings → Secrets and variables → Actions** and add a secret named `METRICS_TOKEN`. Paste the token value.
5. Go to **Actions → Refresh profile dashboard → Run workflow**. The first run creates `github-metrics.svg`; it then refreshes daily.

Without this secret, the dashboard still works using GitHub's built-in token and shows public activity.

GitHub's public contribution graph never exposes the names or details of private repositories. The optional token lets the dashboard include aggregate private activity while keeping private work private.
