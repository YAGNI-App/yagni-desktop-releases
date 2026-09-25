# YAGNI Code

A coding agent that already knows your company.

YAGNI Code works in your repository like any coding agent: it reads code, runs
commands, edits files and opens diffs for you to review. The difference is what
it starts with. It signs in to your YAGNI workspace, so it boots grounded in how
your company and codebase actually work (conventions, decisions, ownership,
priorities) and can ask YAGNI mid-task instead of guessing. The model is routed
through YAGNI too, so there are no API keys to bring.

**This repository is the public home for YAGNI Code:** release downloads for
the desktop app, and the issue tracker for the CLI, the desktop app and the
VS Code extension. The source lives in a private repository.

[Website](https://yagni.app) · [Download the desktop app](https://github.com/YAGNI-App/yagni-desktop-releases/releases/latest) · [Report a bug](https://github.com/YAGNI-App/yagni-desktop-releases/issues/new)

---

## Three ways to use it

All three run the same agent under the same YAGNI login, so your model tiers,
budgets, permission rules and connected tools follow you. Sessions started in
one can be resumed in another.

| | What it is | Get it |
| --- | --- | --- |
| **CLI** | The agent in your terminal. Everything else is built on it. | `npm install -g @yagni-app/code` |
| **Desktop app** | A windowed app with a terminal, diff view and sessions list. macOS (Apple Silicon) and Windows (x64). | [Latest release](https://github.com/YAGNI-App/yagni-desktop-releases/releases/latest) |
| **VS Code extension** | A side panel that knows which file and selection you are looking at. Drives the CLI you installed. | Search **YAGNI Code** in the Extensions view |

## Quick start

You need a [YAGNI account](https://yagni.app) and **Node.js 22.19 or newer**
(`node --version`).

**1. Install the CLI.**

```bash
npm install -g @yagni-app/code
```

Or use the installer, which also fixes an npm global folder your user cannot
write to (common on managed machines) without sudo:

```bash
# macOS / Linux
curl -fsSL https://yagni.app/install.sh | sh
```

```powershell
# Windows (PowerShell)
irm https://yagni.app/install.ps1 | iex
```

**2. Sign in and check your setup.**

```bash
yagni login     # signs you in to your YAGNI workspace with a one-time code
yagni doctor    # a readiness checklist, green or red
```

**3. Start a session in a repository.**

```bash
cd your-repo
yagni
```

From here you can stay in the terminal, open the desktop app, or open the
YAGNI Code panel in VS Code. The desktop app and the extension both pick up
the CLI you just signed in to.

### Windows note

npm installs `yagni` as a PowerShell script, and the default execution policy
on Windows 10 and 11 refuses to run it. The installer tells you when this
applies. The fix is one line for your own account, no administrator needed:

```powershell
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```

If your organization sets the policy through Group Policy, run `yagni.cmd`
instead of `yagni`.

## Desktop downloads

Every release carries these files. The installers are what you want; the rest
feed the app's built-in updater.

| File | For |
| --- | --- |
| `YAGNI-Code-Desktop_aarch64.dmg` | macOS installer, Apple Silicon |
| `YAGNI-Code-Desktop_x86_64.exe` | Windows installer, x64 |
| `*.app.tar.gz`, `*.sig` | The in-app updater. You don't need these. |

Once installed, the app updates itself. Releases tagged `-staging.N` are
prereleases for internal testing and are never marked Latest.

## Report a bug or ask for something

[Open an issue](https://github.com/YAGNI-App/yagni-desktop-releases/issues/new)
and include:

- **Which one:** CLI, desktop app or VS Code extension, and its version
  (`yagni --version`, the app's About screen, or the Extensions view)
- **Your platform:** operating system and `node --version`
- **What happened** and what you expected, with the steps to get there
- **The output of `yagni doctor`**, which covers most setup problems on its own

Please leave out tokens, keys and anything from your workspace you would not
post publicly.

## Security

Don't open a public issue for a vulnerability. Email
**security@yagni.app** instead. We acknowledge reports within two business
days.

## License

YAGNI Code is proprietary software, licensed for use with a YAGNI account. The
full license ships with each package. Installing it from a public registry, or
downloading it from here, does not make it open source.

© YAGNI, Inc.
