# Mockingbyrd tap

A Homebrew cask for [Mockingbyrd](https://mockingbird.marcobuhlmann.com/) — it measures a
workstation running AI agents against one operating doctrine, and can enforce parts of it.

```bash
brew tap marco-buhlmann/mockingbyrd
brew install --cask mockingbyrd
```

Apple silicon, macOS 14 or later. The image is signed with a Developer ID and notarized, so it
installs without a Gatekeeper prompt.

## Upgrading

```bash
brew upgrade --cask mockingbyrd
```

The app checks for new versions itself and will tell you one exists, but it only ever offers a
link — it does not replace itself. So this cask is deliberately **not** marked `auto_updates`,
and `brew upgrade` is what actually moves you forward.

## Uninstalling

```bash
brew uninstall --cask mockingbyrd
```

That removes the app and leaves your data. If you applied the guard fix inside the app, it also
leaves the PreToolUse hook it installed — which keeps running with no app behind it, so calls it
would have asked you about get refused instead. Turn enforcement off in the app first, or remove
everything:

```bash
brew uninstall --zap --cask mockingbyrd
```

## What this repository is

One file: `Casks/mockingbyrd.rb`. It is generated from the download manifest the site publishes
at `/download/latest.json`, so the version and checksum here always describe the image actually
being served rather than whatever was true when someone last edited it by hand.

Issues with the app itself belong on the website, not here.
