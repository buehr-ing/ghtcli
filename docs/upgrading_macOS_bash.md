# Upgrading Bash on macOS

macOS comes with an outdated version of Bash (3.x) due to licensing restrictions. Many modern scripts rely on features from Bash 4 or newer, which are not available by default.

---

## Problem

macOS ships with:

```bash
bash --version
# GNU bash, version 3.2.xx
```

This version lacks features like:
- Associative arrays
- Modern `read` options
- Improved brace expansions
- `globstar` support

---

## Solution: Install Modern Bash via Homebrew

To install the latest version of Bash using [Homebrew](https://brew.sh):

```bash
brew install bash
```

After installation, the new Bash binary will be located at:

```
/opt/homebrew/bin/bash    # Apple Silicon
/usr/local/bin/bash       # Intel Macs
```

---

## Make it your default shell

You must explicitly allow and switch to the new Bash:

### 1. Add new Bash to `/etc/shells` (requires sudo)

```bash
sudo bash -c 'echo /opt/homebrew/bin/bash >> /etc/shells'
```

> Adjust the path if you're on an Intel Mac.

### 2. Change your login shell:

```bash
chsh -s /opt/homebrew/bin/bash
```

You’ll now be using modern Bash by default in all new terminal sessions.

---

## Check your Bash version

```bash
echo $BASH_VERSION
which bash
```
