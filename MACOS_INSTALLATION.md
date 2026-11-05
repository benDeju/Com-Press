# Install Com-Press v1.4.6 on macOS

Publisher: **Benedict S. Leoveras**  
Edition: **Publisher's own private evaluation**  
Installer: `Com-Press-1.4.6-macOS-universal2-Private-Evaluation.pkg`

## Before installing

This guide describes the existing private evaluation package. It does not grant
permission to redistribute it. Review the [agreement](../LICENSE) and
[component notices](../THIRD_PARTY_NOTICES.md).

| Item | Requirement or current status |
| --- | --- |
| System target | macOS 11 Big Sur or later |
| Processors included | Intel `x86_64` and Apple silicon `arm64` |
| Runtime verified | Intel Mac running macOS 11.7.11 |
| Still awaiting runtime tests | Apple silicon and newer macOS versions |
| Free disk space | At least 2 GB before installation, plus space for temporary files and outputs |
| Installer size | Approximately 383 MB (365 MiB) |
| Installed app size | Approximately 1.03 GB |
| Installation access | Administrator authorization may be requested for `/Applications` |

Python and the conversion libraries are included. You do not need to install
Python to use this package. The current app has an ad-hoc signature; the PKG
has no Apple Developer ID signature and is not notarized.

## 1. Verify the package

Use your own build output or another source you have independently verified.
For the existing package, the SHA-256 checksum is:

```text
302079d3f22259a21708cf85dcde1371d3600077ff10bfe254fe27fb816464ea
```

To calculate it, open Terminal in the folder containing the PKG and run:

```sh
shasum -a 256 Com-Press_v1.4.6_Universal.pkg
```

Compare the full result with a checksum obtained independently from the
publisher. A matching checksum confirms the file matches that build; it does
not verify a publisher's identity. A rebuilt or newly signed PKG will have a
different checksum, even if its version number remains the same.

## 2. Install the app

1. Save any ongoing work in Com-Press. From its menu bar icon, choose **Exit**
   and confirm. Close any Python source copy too.
2. Double-click the PKG.
3. Select **Continue**, read the private evaluation agreement, and accept it
   only if you agree with its terms.
4. Follow the Installer prompts. Authorize installation if macOS requests it.
5. Finish the installation. The app is installed at
   `/Applications/Com-Press.app`.

If macOS blocks this unsigned package, first verify its source and checksum.
On Big Sur or Monterey, look under **System Preferences → Security & Privacy →
General** for the available approval control. On versions using System
Settings, look under **Privacy & Security**. Use **Open Anyway** only when you
trust the package and macOS offers that control. A corruption or malware alert
requires investigation; do not treat it as an ordinary approval prompt. Do not
disable Gatekeeper globally. See [Apple's guidance on opening apps](https://support.apple.com/en-us/102445).

The installer attempts to open the setup guide in the logged-in user's GUI
session. An unattended installation without a logged-in user skips this step.
If the guide does not appear, open **Applications → Com-Press**, then select
**Set up Finder wheel…** from its menu bar menu.

## 3. Enable Accessibility

Accessibility lets Com-Press detect the held mouse button or trackpad click
while Finder is active. The user must approve this access.

1. In the guide, click **Open Accessibility settings**.
2. On **Big Sur and Monterey**, use **System Preferences → Security & Privacy →
   Privacy → Accessibility**. Unlock the pane if required.
3. On macOS versions using **System Settings**, open **Privacy & Security** and
   find the relevant app-control permission. Use the guide's button or Settings
   search if your macOS version uses a different label.
4. Enable the installed **Com-Press** app. If it is missing, use **+** to add
   `/Applications/Com-Press.app`.
5. Return to the guide and wait for the listener status to show it is running.
   If macOS explicitly asks you to quit and reopen, follow that instruction.

Enabling Python, Terminal, or a development copy does not automatically grant
access to the installed Com-Press app. Apple explains these controls in its
[privacy settings guide](https://support.apple.com/en-gb/guide/mac-help/mchl211c911f/mac).

## 4. Allow Finder Automation

Finder Automation lets Com-Press read the paths of selected Finder and Desktop
items so the wheel can act on them.

1. In the setup guide, select **Allow Finder access…**.
2. When macOS asks whether Com-Press may control Finder, choose **OK** or
   **Allow**.
3. If you previously denied access, click **Open Automation settings**. Find
   **Com-Press** and enable **Finder**, then retry **Allow Finder access…**.
4. Once both permission statuses are ready, choose
   **Ready — start using the wheel**.

On Big Sur and Monterey, Automation is in **System Preferences → Security &
Privacy → Privacy → Automation**. On versions using System Settings, look under
**Privacy & Security → Automation**. An app may only appear after requesting
access. See [Apple's Automation instructions](https://support.apple.com/en-nz/guide/mac-help/mchl108e1718/mac).

The installer opens the guide; it does not approve either permission for you.

## 5. Try the Finder wheel

1. Open Finder and select a small test file, such as a copy of a picture.
2. Press and hold the **left mouse button**, or physically **click and hold the
   trackpad**, without moving for roughly half a second.
3. The wheel should appear while you are still holding. Resting a finger on
   the trackpad without clicking is insufficient.
4. Choose a category and an action. Follow any file or conversion dialog.
5. Close the Com-Press dashboard with its red close button, keep its menu bar
   icon running, and try again from Finder or the Desktop.

With the hold gesture enabled, the dashboard can stay closed. Moving before
the hold threshold starts a normal Finder drag. The gesture acts on selected
Finder/Desktop items; holding on an empty area or in another app is outside
its intended scope.

## Menu bar commands

| Command | Purpose |
| --- | --- |
| Open Com-Press | Show the dashboard again |
| Open Settings | Open preferences |
| Set up Finder wheel… | Reopen the permission guide |
| Exit | Ask for confirmation, then stop the app and its global gesture |

The app also offers **Choose files or folders and open the action wheel…**.
**Command+Shift+C** opens its picker while Com-Press is active. The shortcut is
not registered system-wide.

## Troubleshooting

| Symptom | What to check |
| --- | --- |
| Menu bar icon is present, but no wheel appears | Confirm the hold gesture and wheel are enabled in Preferences. Reopen setup and check both permissions for `/Applications/Com-Press.app`. Select an actual Finder/Desktop file and hold without moving. |
| Wheel only works in the dashboard | Check Accessibility for the installed app, rather than a Python or development copy. Approve Finder Automation too. |
| Finder is missing from Automation settings | Run **Allow Finder access…** so macOS can request it. |
| Permission was enabled but the guide still reports it is missing | Quit through **Exit**, confirm, and reopen the installed app. If its entry is stale after replacing the app, remove that Com-Press entry from Accessibility and add the installed app again. |
| Dashboard does not reopen or appears blank | Use **Open Com-Press** from the menu bar. If it persists, exit and reopen the installed app, then report the app version, macOS version, and recent log entries. |
| 7Z creation is unavailable | Install a compatible 7-Zip command and make it discoverable as `7zz`, `7z`, `7za`, or `7zr` on the app's `PATH`. |
| DOCX-to-PDF layout differs | Use a compatible LibreOffice installation with `soffice` or `libreoffice` discoverable on the app's `PATH`. The built-in fallback handles basic text and tables. |
| A media format fails to convert | Try a small known-good file and another format. Intel and Apple silicon use different FFmpeg engine versions; Apple silicon execution testing remains pending. |

For an app opened from Finder, command-line tools may not inherit the `PATH`
you configured in Terminal. Microsoft Word automation is implemented only on
Windows; installing Word for Mac does not enable that backend.

The macOS application log is at:

```text
~/Library/Logs/Com-Press/com_press.log
```

Review log entries before posting them to GitHub; they may include local file
paths. For a report, include the processor family, macOS version, app version,
selected action, and whether the dashboard was open.

## Update or uninstall

Before updating, exit Com-Press from the menu bar and confirm. Run the new PKG;
it replaces `/Applications/Com-Press.app` while retaining saved preferences.
Check the new package's checksum and repeat permission setup if macOS requests
it after the replacement.

To uninstall, choose **Exit**, confirm, then move **Com-Press.app** from
Applications to the Trash. User preferences, logs, and converted output files
are retained. Review Accessibility and Automation settings if you want to
remove permissions for the deleted app.

## License files

The installed agreement and bundled component notices are in:

```text
/Applications/Com-Press.app/Contents/Resources/legal
```

No activation key, purchase, online activation, or automatic expiry is included.
The evaluation agreement does not resolve third-party distribution obligations.
