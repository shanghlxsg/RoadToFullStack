# Software setup

## Xcode

Xcode is **the** developer tools for all macOS systems. Go to `Dock > Launchpad > App Store > Xcode > Install`.

## Homebrew + Xcode CLI Tools

Homebrew (or `brew`) is the equivalent of Linux package manager `apt` in Ubuntu.

```zsh
# expect command not found:
brew

# see official website for more info <https://brew.sh>
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Xcode Command Line Tools will be prompted to be installed with Homebrew.
```

## Rosetta

```zsh
softwareupdate --install-rosetta --agree-to-license

# open shell with Rosetta
arch -x86_64 zsh

# check terminal instructions architecture (expect i386)
arch
```

[Why OS X displays `i386`](https://stackoverflow.com/questions/12763296/os-x-arch-command-incorrect).

## curl

*Bundled with macOS.*

## wget

```zsh
brew install wget
```

## SSH

Source: <https://docs.github.com/en/authentication/connecting-to-github-with-ssh/>

Note: SSH is bundled with macOS terminal and there is no need for additional installation.

```zsh
# expect no response
ls -al ~/.ssh

ssh-keygen -t ed25519 -C "your_email@example.com"

# start ssh-agent in background
eval "$(ssh-agent -s)"

# check if file exists
open ~/.ssh/config
# if file does not exist:
touch ~/.ssh/config
# add the following into the file:
Host *.github.com
  AddKeysToAgent yes
  UseKeychain yes # remove this line if not storing SSH passphrase in Keychain
  IdentityFile ~/.ssh/id_ed25519

ssh-add ~/.ssh/id_ed25519
cat ~/.ssh/id_ed25519.pub
```

## Tree

Previews folder structure in tree format

```zsh
brew install tree
```

## Git

Git is shipped with [Xcode](#xcode) in macOS.

```bash
# configuration:
git config --global user.name "your_username"
git config --global user.email your_email@example.com
```

## GitHub

### GitHub With HTTPS & PAT

Note that GitHub no longer supports password authentication since 2021. To perform `git clone` with GitHub, use PATs (Personal Access Tokens) instead.

### GitHub With SSH

Ensure that your SSH key is created with the correct email. See [section on SSH](#ssh) and copy the entire content of the `~/.ssh/id_ed25519.pub` file from the last step.

Go to <https://github.com/settings/keys>, create a new SSH key and paste the contents from the previous step.

To use git with any (permitted) repositories, use the URL for `Clone with SSH`.

If you have already cloned with HTTPS:

```zsh
cd ~/<project directory>
git remote set-url origin <URL>
```

### GitHub Desktop

[Source](https://desktop.github.com/).

GUI for using Git with GitHub. Works well for MacOS, sucks for Ubuntu.

## VS Code

Install via official `.app` file (see [docs](https://code.visualstudio.com/docs/setup/mac)).

To launch VS Code from macOS terminal, open VS Code Command Palette `Cmd+Shift+P` and type `shell command` to install `code` command in `$PATH`.

### Using Rosetta Shell For VS Code Terminal

[Install Rosetta](1-initial-setup.md#rosetta).

*To prevent incompatiblity with Apple silicon chips, it is wise to use Rosetta for all software development projects regardless.*

To update VS Code default terminal to run on Rosetta shell, go to Command Palette (Cmd+Shift+P) and search for `settings.json`. Select `Open User Settings (JSON)` or `Open Default Settings (JSON)`. Append the following lines:

```json
"terminal.integrated.profiles.osx": {
    "x86_64 zsh": {
        "path": "/usr/bin/arch",
        "args": [
            "-arch",
            "x86_64",
            "/bin/zsh"
        ]
    }
},
"terminal.integrated.defaultProfile.osx": "x86_64 zsh"
```

## Python Version Manager

```zsh
brew update
brew install pyenv

# setup shell environment for pyenv
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init -)"' >> ~/.zshrc
# restart to take effect
exec "$SHELL"

# installing specific versions
pyenv install 3 # latest version 3.x.x
pyenv install 3.9 # latest sub-version 3.9.x
pyenv install 3.8.15 # specific release

# select python version
pyenv global 3.9.15

# show all versions (including current selection)
pyenv versions

```

## Postman (API Tester)

Download from [official source](https://www.postman.com/downloads/) in `.zip` format, extract and copy the `Application` file into `Finder > Applications`

## Virtual Machine

* [Parallels](https://www.parallels.com/) (paid).
* [VMWare Fusion](https://www.vmware.com/asean/products/fusion.html) (paid).

## Chrome

Install via official `.dmg` file.
