# Android CI/CD with GitHub Actions & Firebase App Distribution

This demo app showcases how to set up CI/CD for Android using GitHub Actions and Firebase App Distribution. It includes building variants (`debug`, `preProd`, `release`) and distributing APKs automatically to testers.

Each build variant has its own workflow and can be triggered manually.

---

## 📦 Features

- GitHub Actions CI/CD workflow
- Firebase App Distribution integration
- Multiple build variants support
- Upload release notes
- Manual or auto trigger support
- Secure with GCP Service Account via GitHub Secrets


## 🛠️ Setup Overview

Three workflow files are located in `.github/workflows/`:

- `build-debug.yml`
- `build-preprod.yml`
- `build-release.yml`

Each file:
- Builds a specific variant (`assembleDebug`, `assemblePreProd`, or `assembleRelease`)
- Runs on manual trigger using `workflow_dispatch`
- Uploads the APK as a downloadable artifact and on firebase app distribution 

---

#### Firebase Credentials Setup : https://github.com/wzieba/Firebase-Distribution-Github-Action/wiki/FIREBASE_TOKEN-migration

## Add Secret to GitHub

- Open your GitHub repo → Settings → Secrets → Actions

| 🔐 **Secret Name**           | 💡 **Value**                                                                 |
|-----------------------------|------------------------------------------------------------------------------|
| `CREDENTIAL_FILE_CONTENT`   | Paste the full JSON content of the Firebase service account key              |
| `FIREBASE_APP_ID`           | Get it from **Firebase Console → Project Settings → General → App ID**       |
| `TESTERS_EMAILS`            | Comma-separated emails, e.g., `user1@example.com,user2@example.com`          |



## ▶️ How to Trigger a Build

1. Push your code to GitHub.
2. Go to your repo's **Actions** tab.
3. Select the workflow (e.g., `Build Debug APK`).
4. Click **“Run workflow”**.
5. Choose the branch and click **“Run workflow”**.

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

<img width="600" alt="Screenshot 2025-04-18 at 11 39 01 PM" src="https://github.com/user-attachments/assets/c803b7e0-4014-46c8-8762-181d1f0cc347" />
<img width="500" alt="Screenshot 2025-04-18 at 11 34 06 PM" src="https://github.com/user-attachments/assets/e25abed6-2f8a-4ea5-a14d-56219bf052d8" />
<img width="300" alt="Screenshot 2025-04-18 at 11 36 23 PM" src="https://github.com/user-attachments/assets/79913cec-ab3a-426d-b0e7-87e6e5d3f072" />
<img width="600" alt="Screenshot 2025-04-18 at 11 39 19 PM" src="https://github.com/user-attachments/assets/c9461d35-490b-441a-a7fc-63dec3489a58" />




