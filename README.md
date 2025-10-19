# ghtcli

**ghtcli** installs and keeps CLI tools for Docker, Kubernetes, and Talos Linux up to date — directly from official GitHub releases.

---

## 📦 Installation

```bash
curl -s ghtcli.sh | bash -s install ghtcli
```

The script installs itself as `ghtcli` (typically under `~/.local/bin`).

To use `ghtcli` and other installed tools from the command line, the directory `~/.local/bin` must be in your shell's `$PATH`.

### 🐧 Linux

Most modern Linux distributions (like Ubuntu, Debian, Arch) already include `~/.local/bin` if it exists. If not, add this to your `~/.bashrc`, `~/.bash_profile`, or `~/.zshrc`:

```bash
export PATH="$HOME/.local/bin:$PATH"
```

Then reload your shell:

```bash
source ~/.bashrc    # or ~/.zshrc, etc.
```

### 🍎  macOS

**Note:** For macOS users, be aware that the system still includes Bash 3.x.

[Read how to upgrade to Bash 5+ with Homebrew](docs/upgrading_macOS_bash.md)

macOS does **not** include `~/.local/bin` in the default `$PATH`. To add it, append this to your `~/.zprofile` or `~/.zshrc`:

```bash
export PATH="$HOME/.local/bin:$PATH"
```

Then restart your terminal or run:

```bash
source ~/.zshrc
```

> You can verify it with: `echo $PATH` or `which ghtcli`

---

## 🚀 Usage

**Note:** For subcommands that accept `<tools>` (like `install`, `remove`, `clean`, `list`, and `info`), you can omit `<tools>` to apply the command to **all available or installed tools**.

This does **not** apply to commands that don't take `<tools>` (e.g., `update`, `autoupdate`).

```bash
ghtcli install <tools>
ghtcli completion <tools>
ghtcli remove <tools>
ghtcli clean <tools> # Clean up cached downloads
ghtcli list <tools>  # Show all available tools and groups
ghtcli info <tools>  # Show GitHub metadata for tools
ghtcli help

ghtcli update        # Update installed tools to latest
ghtcli autoupdate (enable|disable) # Enable or disable autoupdate with cron
```

### Example:

```bash
ghtcli install talosctl kubectl
ghtcli list kube,talos skopeo 
ghtcli info k9s
ghtcli remove ttx
```

---

## 🛠 Supported Tools (Selection)

- `talosctl`
- `kubectl`
- `k9s`
- `flux`
- `stern`
- `ttx`
- `helm`
- `jq`
- `mc`
- `yq`
- `skopeo`
- and more...

Tools are fetched from GitHub releases, unpacked, and placed into your local `$PATH` (e.g., `~/.local/bin`).

---

## 🧹 Removal

```bash
ghtcli remove
```

---

## ⚖️  License

This project is licensed under the [MIT License](LICENSE).

© 2025 Marcel Buehring

---

## 👤 Author

Marcel Buehring
GitHub: [@buehr-ing](https://github.com/buehr-ing)
