# GitHub Actions: Android Build Variants

This project uses **GitHub Actions** to build Android APKs for multiple build variants: `debug`, `preProd`, and `release`.

Each build variant has its own workflow and can be triggered manually.

---

## 🛠️ Setup Overview

Three workflow files are located in `.github/workflows/`:

- `build-debug.yml`
- `build-preprod.yml`
- `build-release.yml`

Each file:
- Builds a specific variant (`assembleDebug`, `assemblePreProd`, or `assembleRelease`)
- Runs on manual trigger using `workflow_dispatch`
- Uploads the APK as a downloadable artifact

---

## ▶️ How to Trigger a Build

1. Push your code to GitHub.
2. Go to your repo's **Actions** tab.
3. Select the workflow (e.g., `Build Debug APK`).
4. Choose the branch and click **“Run workflow”**.

GitHub Actions will then:
- Build your project for the selected variant
- Generate an APK
- Upload it for download

---

## 📦 Download APK Artifacts

Once the workflow finishes, you can:
- Click the workflow run
- Scroll to the **Artifacts** section
- Download the generated APK (`.apk`)

---

## ✅ Requirements

- Android project with build variants defined (e.g., `debug`, `preProd`, `release`)
- GitHub repository with Actions enabled
- Gradle configured to build the required flavors

---

## 📁 Directory Structure

```bash
.github/
└── workflows/
    ├── build-debug.yml
    ├── build-preprod.yml
    └── build-release.yml
```
