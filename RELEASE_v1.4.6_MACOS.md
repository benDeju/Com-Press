# Com-Press v1.4.6 — macOS Universal2 Private Evaluation

**Publisher: Benedict S. Leoveras**

Com-Press combines compression and document, picture, audio, and video conversion
in a radial wheel. The Finder/Desktop hold gesture keeps those actions
available while the dashboard is closed and Com-Press remains in the menu bar.

## Release status

This is a record of the publisher's own private evaluation build, not approval
to distribute its installer. The current Apple silicon FFmpeg engine enables
nonfree components and must be replaced or rebuilt with a redistributable
configuration before sharing the package. PyMuPDF/MuPDF and the other bundled
components also retain their own license obligations. See the
[component notices](../THIRD_PARTY_NOTICES.md).

## Included in this build

- Universal2 app with Intel and Apple silicon code and a macOS 11 Big Sur
  deployment target.
- Finder/Desktop wheel triggered by holding the left mouse button or trackpad
  click, including while the dashboard is closed.
- First-launch Accessibility and Finder Automation setup guide, also available
  from the menu bar.
- Menu bar commands for opening the dashboard, opening settings, permission
  setup, and exiting with confirmation.
- Bundled Python runtime, Qt interface, artwork, conversion libraries, and
  media engine.
- Private evaluation agreement naming Benedict S. Leoveras as publisher; no
  license key or online activation.

## Package details

| Item | Value |
| --- | --- |
| Package filename | `Com-Press_v1.4.6_Universal.pkg` |
| App location | `/Applications/Com-Press.app` |
| CPU architectures | `x86_64` and `arm64` |
| Minimum deployment target | macOS 11.0 |
| Approximate download size | 383 MB / 365 MiB |
| Approximate installed size | 1.03 GB |
| Apple Developer ID signed | No |
| Notarized | No |

SHA-256 of the current PKG:

```text
302079d3f22259a21708cf85dcde1371d3600077ff10bfe254fe27fb816464ea
```

This checksum identifies the existing build. Update it whenever the PKG is
rebuilt or signed.

## Installation

1. Exit the previous copy of Com-Press from its menu bar and confirm.
2. Open the PKG, review the evaluation agreement, and complete installation.
3. Open the installed app and follow its wheel setup guide.
4. Enable Accessibility for `/Applications/Com-Press.app` and allow Finder
   Automation. macOS requires the user to grant these permissions.
5. Select a Finder/Desktop file, then click and hold for about half a second.

See the [full installation guide](MACOS_INSTALLATION.md).

## Validation and limits

The native audit found both CPU slices in all **238** bundled native binaries
and deployment targets no newer than macOS 11. Packaged Intel checks passed
native imports, sample ZIP creation, selected document and image conversions,
FFmpeg audio conversion, and Qt dashboard construction and rendering on
**macOS 11.7.11 Big Sur**.

Apple silicon execution and newer macOS runtime testing remain pending. An
architecture and deployment-target audit does not establish runtime behavior
on every supported Mac. Intel uses FFmpeg 7.1; Apple silicon uses an older
FFmpeg 4.4 compatibility engine. Optional 7Z creation needs a separate 7-Zip
command, and LibreOffice improves Word-to-PDF layout on macOS.

The local build's release manifest, binary audit, runtime check, validation
report, and checksum list are generated in `dist/`. This documentation change
does not rebuild or re-sign that package.
