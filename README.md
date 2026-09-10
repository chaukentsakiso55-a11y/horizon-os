# HORIZON OS 4.0 ULTIMATE

Android device-testing build of HORIZON OS.

## Automatic APK build

Every push to `main` and every manual workflow run starts **Build HORIZON OS APK** in GitHub Actions. When the run succeeds, download the `HORIZON-OS-debug-apk` artifact to get `app-debug.apk`.

The Android source is stored as verified split archive parts under `source-parts/`. The workflow reconstructs `horizon_android_optimized.tar.xz`, verifies SHA-256 `a9c0963994ef67d768f50dec12d92cec2607aea77ed2eb3d9745a8734b05c792`, extracts the `android/` project, and runs `assembleDebug` with Java 17 and Gradle 8.9.

Android permissions are requested through normal runtime permission prompts. Permissions and system capabilities that Android restricts remain controlled by the device and Android security model.
