# Notebook Cell Sound

A VS Code / Kiro extension that plays a sound when a Jupyter notebook cell finishes execution. Perfect for long-running cells where you want audio feedback when they complete!

## Demo

https://github.com/user-attachments/assets/b04cb905-dbd9-414c-b048-8cb5c4c38a50

## Features

- 🔔 **Automatic Sound Notification** — Plays a sound when any notebook cell completes
- 🎵 **Customizable Sounds** — Use your own sound files (WAV, MP3, OGG, AIFF, M4A)
- ✅ **Success/Error Sounds** — Different sounds for successful execution vs errors
- 🔊 **Volume Control** — Adjust volume from 0% to 100%
- 🎛️ **Easy Toggle** — Quickly enable/disable via command palette
- 💻 **Cross-Platform** — Works on macOS, Windows, and Linux

![Cell Sound Demo](images/demo.gif)

## Installation

### From VS Code Marketplace

1. Open VS Code / Kiro
2. Go to Extensions (`Cmd+Shift+X` / `Ctrl+Shift+X`)
3. Search for **"Notebook Cell Sound"**
4. Click **Install**

### From VSIX File

1. Download the `.vsix` file from [Releases](https://github.com/piashsarker/cell-completion-sound/releases)
2. Open Command Palette (`Cmd+Shift+P` / `Ctrl+Shift+P`)
3. Run **"Extensions: Install from VSIX..."**
4. Select the downloaded `.vsix` file
5. Click **Reload** when prompted (or run "Developer: Reload Window")

### Build from Source

If you want to build the extension yourself:

```bash
# Clone the repo
git clone https://github.com/piashsarker/cell-completion-sound.git
cd cell-completion-sound

# Install dependencies
npm install

# Compile TypeScript
npm run compile

# Package as .vsix (requires vsce)
npm install -g @vscode/vsce
vsce package --allow-missing-repository
```

This will generate a `notebook-cell-sound-x.x.x.vsix` file in the project root.

#### Install the built .vsix in VS Code / Kiro

**Option 1: Command Palette**
1. Open VS Code or Kiro
2. Press `Cmd+Shift+P` (macOS) or `Ctrl+Shift+P` (Windows/Linux)
3. Type **"Extensions: Install from VSIX..."** and select it
4. Browse to the `.vsix` file and select it
5. Reload the window when prompted

**Option 2: CLI**
```bash
code --install-extension notebook-cell-sound-1.0.1.vsix
```

For Kiro:
```bash
kiro --install-extension notebook-cell-sound-1.0.1.vsix
```

## Usage

Once installed, the extension automatically plays a sound when any notebook cell finishes executing. No configuration needed!

### Commands

Open the Command Palette (`Cmd+Shift+P` / `Ctrl+Shift+P`) and search for:

| Command | Description |
|---------|-------------|
| `Cell Sound: Toggle Sound On/Off` | Enable or disable the completion sound |
| `Cell Sound: Select Custom Sound File` | Choose a custom sound for successful completions |
| `Cell Sound: Select Custom Error Sound File` | Choose a custom sound for errors |
| `Cell Sound: Test Current Sound` | Play the current sound to test it |
| `Cell Sound: Show Debug Logs` | View extension logs for troubleshooting |

### Settings

Configure in Settings (`Cmd+,` / `Ctrl+,`) → search "Cell Sound":

| Setting | Default | Description |
|---------|---------|-------------|
| `cellCompletionSound.enabled` | `true` | Enable/disable the completion sound |
| `cellCompletionSound.soundFilePath` | `""` | Path to custom success sound file |
| `cellCompletionSound.errorSoundFilePath` | `""` | Path to custom error sound file |
| `cellCompletionSound.volume` | `0.5` | Volume level (0.0 to 1.0) |
| `cellCompletionSound.playOnSuccess` | `true` | Play sound on successful execution |
| `cellCompletionSound.playOnError` | `true` | Play sound on failed execution |

## Custom Sounds

### Using Your Own Sounds

1. Open Command Palette
2. Run `Cell Sound: Select Custom Sound File`
3. Browse to your sound file
4. Done! The extension will use this sound going forward

### Supported Formats

- WAV (recommended)
- MP3
- OGG
- AIFF
- M4A

### Free Sound Resources

- [Freesound.org](https://freesound.org/)
- [Mixkit](https://mixkit.co/free-sound-effects/)
- [Zapsplat](https://www.zapsplat.com/)

## Platform Notes

| Platform | Audio Player | Notes |
|----------|--------------|-------|
| **macOS** | `afplay` (built-in) | Full volume control |
| **Windows** | PowerShell `Media.SoundPlayer` | WAV files work best |
| **Linux** | `paplay`, `aplay`, or `ffplay` | Install at least one |

## Troubleshooting

**No sound plays?**
1. Run `Cell Sound: Test Current Sound` to verify audio works
2. Check that the extension is enabled in settings
3. On Linux, ensure `paplay`, `aplay`, or `ffplay` is installed
4. Check your system volume

**Custom sound doesn't work?**
1. Verify the file path is correct
2. Try a WAV file (most compatible)
3. Check file permissions

## Contributing

Contributions welcome! Please open an issue or submit a pull request.

## License

[MIT License](LICENSE)

---

**Enjoy coding with audio feedback! 🔔**
