# Road to 5.4 — Marco Vieira
Offline personal Android training app: dark theme, 26 daily exercise tables, notes and manual backup/import. Android 6+; no native libraries, no runtime network permission. External HTTPS guidance opens in a browser.

## Build on GitHub
1. Add the repository secrets ROAD54_KEYSTORE_BASE64 and ROAD54_KEYSTORE_PASSWORD from your private setup files. Never commit signing material.
2. Actions → Build Android APK → Run workflow.
3. Open the successful run and download Road54-Marco-Vieira-APK under Artifacts. Extract and install the APK.

Uses Android Gradle Plugin 8.7.3, Gradle 8.9 and Java 17. The workflow installs Android SDK 35, compiles Java/resources, runs Android lint, verifies APK signatures and alignment, then uploads the APK. No Gradle wrapper is needed for this workflow; setup-gradle supplies Gradle.

Application ID remains uk.marco.roadto55. The supplied PRIVATE-SETUP key is the same as the Personal APK; version codes start at 101. The original uploaded Road-to-5.4 app has a different ID and cannot be upgraded by this project. Keep this same key for future updates; a replacement key will cause a signing conflict. Keep the same repository so run numbers continue increasing, or explicitly raise versionCode if moving repositories.

The local HTML origin, filename and record key remain unchanged to support existing Personal records. Back up before updating. Device-specific install failures still need the full Android error to diagnose; a successful GitHub build does not prove installation on your phone.

## Editing
Training page: app/src/main/assets/index.html
Android wrapper: app/src/main/java/uk/marco/roadto55/MainActivity.java
Icon: app/src/main/res/mipmap-*/ic_launcher.png

## Validation status
Project structure, Java compilation against an Android API jar, manifest XML, workflow syntax and source assets checked locally. The full Android Gradle build and Samsung installation must be validated by the workflow and your device.

## References
https://developer.android.com/build/releases/agp-8-7-0-release-notes
https://docs.github.com/en/actions/how-tos/manage-workflow-runs/download-workflow-artifacts
