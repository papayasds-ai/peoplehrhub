PeopleHub - HR management for Windows and Android
==================================================

1) WINDOWS  ->  double-click  Build-Windows.bat
   Click "Yes" on the administrator prompt. It downloads portable Node.js, builds the
   app and opens PeopleHub-Setup.exe (the installer). Needs internet, 5-10 minutes.

2) ANDROID  ->  double-click  Build-Android.bat
   Downloads portable Java + Android SDK into .tools (about 1.5 GB the first time) and
   produces PeopleHub.apk in this folder. Copy it to your phone and open it
   (allow "install unknown apps" once). 10-20 minutes the first time, ~3 after.

Nothing is installed on your PC by the Android build; no manual steps are needed.
If a build fails, the log is saved as build-windows.log / build-android.log.
Tip: keep this folder on a short path such as C:\PeopleHub.

FIRST START
  Create your company + admin account (tick "demo data" to explore with sample people).
  Demo logins (password welcome1): amina.rahman@demo.co (HR admin),
  marcus.lee@demo.co (manager), david.chen@demo.co (employee).

WHAT IS INSIDE
  Home dashboard (clock, balances, approvals, who's out, birthdays, to-dos, news,
  shout-outs, pulse survey) - People directory + rich profiles (job history, pay,
  documents, emergency contact) - Org chart - Time off (policies, balances, approvals,
  team calendar, holidays) - Time tracking (clock, timesheets, overtime) - Hiring
  (job openings, drag-and-drop pipeline, hire -> profile + onboarding) - Onboarding /
  offboarding checklists - Goals and reviews - Reports (headcount, turnover, tenure,
  eNPS, CSV, print/PDF) - Settings - 3 roles: Admin, Manager, Employee.

ONEDRIVE BACKUP (instead of Google Drive) - no ID, no sign-in code, one button
  Settings > Backup & updates > "Back up to OneDrive".
  Windows: saves into OneDrive/PeopleHub through the OneDrive app already signed in on the
  PC (also an automatic daily copy); Restore reads it back.
  Android: opens the share menu - pick OneDrive. Restore opens the file picker.
  (Optional: onedrive-client-id.txt enables a direct Microsoft account sign-in instead.)

UPDATES (OTA via your GitHub repo + release "ota")
  Repo:    https://github.com/papayasds-ai/peoplehrhub
  Release: https://github.com/papayasds-ai/peoplehrhub/releases/tag/ota
  To publish a new version: double-click  Push-Update.bat
     - asks for the version (e.g. 1.0.1) and a one-line "what's new"
     - the first time, a browser window asks you to sign in to GitHub (portable GitHub CLI, nothing to install)
     - builds the Windows installer, then uploads it, latest.yml, the Android web update and update.json
  Installed apps then update themselves: Windows via the installer, Android web-layer instantly,
  APK on request (answer "y" to upload PeopleHub.apk; build it first with Build-Android.bat).
  Command line alternative:  node scripts/push-update.js 1.0.1 "What's new" --win dist

CHANGES IN 1.0.1
  Org chart fits the screen: auto-fit on Windows (zoom -/+, Fit, Ctrl+wheel, drag, pinch),
  folded branches (+N / - buttons, Collapse / Expand all), and an indented list layout on phones.
