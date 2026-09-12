# Homebrew Wine Tap

A Homebrew tap providing Wine packages (`wine-stable`, `wine@devel`, and `wine@staging`) that were disabled in the official Homebrew Cask repository due to macOS Gatekeeper checks.

## Casks Included

- **`wine-stable`**: Stable releases of Wine for macOS (WineHQ)
- **`wine@devel`**: Development releases of Wine for macOS
- **`wine@staging`**: Staging releases of Wine for macOS (includes experimental features and patches)
- **`gstreamer-runtime`**: GStreamer multimedia framework runtime package (Wine dependency)
- **`gstreamer-development`**: GStreamer development package


## Requirements

- macOS (Apple Silicon or Intel)
- On Apple Silicon (M1/M2/M3/M4/etc.), Rosetta 2 must be installed:
  ```bash
  softwareupdate --install-rosetta
  ```
- `gstreamer-runtime` cask dependency (automatically handled by brew)

## Installation

### 1. Add the Tap

```bash
brew tap philberthfz/wine
```

*(If Homebrew 6+ prompts that the tap is untrusted, run:)*
```bash
brew trust philberthfz/wine
```

### 2. Install Wine

Choose the Wine flavor you want:

```bash
# Stable version
brew install --cask wine-stable

# Development version
brew install --cask wine@devel

# Staging version
brew install --cask wine@staging
```

> **Note on Gatekeeper / Quarantine:**
> Since these builds do not pass macOS Gatekeeper notarization checks, macOS may display a security prompt or block execution. If needed, you can bypass quarantine during installation:
> ```bash
> brew install --cask --no-quarantine wine-stable
> ```
> Or manually remove the quarantine attribute:
> ```bash
> xattr -dr com.apple.quarantine "/Applications/Wine Stable.app"
> ```

## Attribution & Credits

- The cask definitions (`wine-stable`, `wine@devel`, `wine@staging`, `gstreamer-runtime`, and `gstreamer-development`) were originally authored and maintained by the [Homebrew](https://github.com/Homebrew/homebrew-cask) maintainers and community under the BSD-2-Clause license.
- macOS Wine builds and release packages are provided by [Gcenx](https://github.com/Gcenx/macOS_Wine_builds) and the [WineHQ](https://wiki.winehq.org/MacOS) project.
- macOS GStreamer official packages are provided by the [GStreamer / freedesktop.org](https://gstreamer.freedesktop.org/) project.
- Tap configuration and re-enabling adjustments were prepared with the assistance of Gemini (Google Antigravity).


