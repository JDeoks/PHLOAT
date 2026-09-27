---
name: phloat-setup
description: Install PHLOAT and enable its Quick Look extension.
---
<!-- Created by JDeoks on 9/27/26. -->

# Install PHLOAT and enable Quick Look

## Install

Skip this step if PHLOAT is already installed.

1. Locate and mount the downloaded PHLOAT DMG.
2. Copy `PHLOAT.app` to the Applications folder.
3. Open the installed app once and eject the DMG.

## Enable

Adjust the path to match the actual installation, then run:

```sh
phloat_app='/Applications/PHLOAT.app'
pluginkit -a "$phloat_app/Contents/PlugIns/PHLOATQuickLook.appex"
pluginkit -e use -i com.jdeoks.phloat.QuickLook
qlmanage -r
qlmanage -r cache
pluginkit -m -v -p com.apple.quicklook.preview -i com.jdeoks.phloat.QuickLook
```

Confirm that the registered extension path points to the installed app. If manual activation is needed, direct the user to enable PHLOAT in **System Settings → General → Login Items & Extensions → Quick Look**.

## Verify

Ask the user to select a Markdown file in Finder and press **Space** to verify the preview.

If it does not work, check for duplicate registrations and inspect execution logs, then report the findings.
