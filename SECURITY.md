# Security Policy

## Supported versions

Security fixes go into the newest release only. Installed apps (Mac and Windows, 1.3.0 and later) check for updates twice a day and install them with one click, so staying current is easy.

| Version | Security fixes |
| ------- | -------------- |
| 1.3.x (latest) | Yes |
| 1.2.x and older | No: please update. These versions can't update themselves; install the latest release once by hand. |

Installers: <https://github.com/Neer171/download-manager-releases/releases/latest>

## Reporting a vulnerability

Please report security problems **privately**, not in a public issue:

1. Go to <https://github.com/Neer171/download-manager-releases/security/advisories/new> (on the repository page: **Security → Report a vulnerability**). You need a free GitHub account.
2. Describe the problem, the version and system (Mac, Windows or Linux, and the browser if the extension is involved), and the steps to reproduce it. A proof of concept helps.

What happens next:
- We aim to reply within 7 days.
- If the report is confirmed, we fix it in a new release and aim to ship serious issues within 30 days. Installed apps then offer the update automatically.
- We'll tell you when the fix is out and credit you in the release notes, unless you prefer not to be named.
- If we decide it isn't a security problem, we'll explain why.

Please give us a chance to release a fix before you talk about the problem publicly.

## How Download Manager protects you

- **Local only.** The app's engine listens only on your own computer (`127.0.0.1:4430`). It refuses requests from websites, DNS-rebinding tricks and other browser extensions, and accepts only its own window, its own extension (fixed ID in Chromium browsers, a key you approve once in Firefox) and programs running on your computer.
- **Signed updates.** Updates are installed only if the version list is signed with Download Manager's private update key and every installer matches its signed SHA-256 checksum.
- **Downloads are marked as coming from the internet**, as browsers do, so macOS Gatekeeper and Windows SmartScreen still check a downloaded app or script before it runs.
- **Bundled tools are verified.** Node.js, yt-dlp and ffmpeg are pinned versions whose official checksums are checked when the installers are built.
- **No accounts, analytics or telemetry.** The only automatic network requests are the update checks (Download Manager twice a day, yt-dlp once a day); automatic Download Manager checks can be turned off in Settings.
- **Login cookies stay local.** Cookies used for logged-in downloads go only to the site being downloaded from, are kept only until the download finishes or is removed, and are never passed on the command line.
- **DRM is not bypassed.** Copy-protected video (Netflix, Disney+, Prime Video and similar) is detected and not downloaded.

## Out of scope

- Problems that need someone to already control your user account or computer (any local program can use the engine, just as it could use your files).
- Sites changing in ways that break video downloads: that's an ordinary bug, not a security issue.
- The bundled third-party programs (Node.js, yt-dlp, ffmpeg): please report their own vulnerabilities to those projects. We'll ship their fixed versions.
