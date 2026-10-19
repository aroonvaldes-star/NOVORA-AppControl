# LINK Control

Android companion of NOVORA-LINK. Canonical development currently lives in the NOVORA-LINK checkout.
Keep src/NOVORA.Android and its linked shared source/resources under src/NOVORA synchronized.
Do not commit bin, obj, target, APK outputs, secrets or signing keys.
Build Release ARM64 with target Compile for source verification; do not produce a newly signed APK in CI.
New distributable APKs require N+1 version/code, stable signing identity and an explicit release process.
