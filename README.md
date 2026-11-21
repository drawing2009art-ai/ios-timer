# Timer — iOS wrapper (Capacitor)

This project packages the supplied `index.html` web app inside a native iOS shell using Capacitor. The app's HTML, CSS, JavaScript, IndexedDB and localStorage code are kept as supplied.

## Build from Windows with GitHub Actions

1. Create a new GitHub repository and upload the contents of this folder (not the folder itself).
2. In `capacitor.config.ts`, replace `com.example.timer` with a unique reverse-domain app ID, for example `com.yourname.timer` (letters, numbers and dots; no spaces).
3. Commit the changes to `main` (or `master`).
4. Open the repository's **Actions** tab and run **Build iOS app (unsigned)**, or push a commit to the main branch.
5. When the workflow finishes, open its run and download the `Timer-unsigned-iOS-archive` artifact.

GitHub Actions runs the build on a hosted macOS machine, so you do not need to own a Mac.

## Important: signing and installing

The workflow intentionally creates an **unsigned** iOS archive. It proves the Capacitor project can be compiled, but it is **not an installable IPA**. iPhones require an app signed with a valid Apple development/distribution certificate and provisioning profile. Those signing credentials must come from the Apple account that will install/distribute the app; do not put passwords or certificates in the repository. A later signed-export workflow can be configured once the appropriate Apple signing method and account are ready.

For personal testing, Apple's free Personal Team signing has limitations and provisioning typically needs renewal after 7 days. Public distribution uses Apple's paid developer program and App Store/TestFlight requirements.

## Notes

- App display name: `Timer`
- Web entry point: `www/index.html`
- Capacitor config: `capacitor.config.ts`
- The app uses browser storage APIs. Data is stored locally on the device/webview and is not automatically synchronized between devices.
- The Roboto Flex font is loaded from Google Fonts; the app can use its system fallback if the network is unavailable.
