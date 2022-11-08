# Software setup

## Xcode

Xcode is **the** developer tools for all MacOS systems. Go to `Dock > Launchpad > App Store > Xcode > Install`.

## Homebrew + Xcode CLI Tools

Homebrew (or `brew`) is the equivalent of Linux package manager `apt` in Ubuntu.

```zsh
# expect command not found:
brew

# see official website for more info <https://brew.sh>
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Xcode Command Line Tools will be prompted to be installed with Homebrew.
```

## SSH

Source: <https://docs.github.com/en/authentication/connecting-to-github-with-ssh/>

Note: SSH is bundled with MacOS terminal and there is no need for additional installation.

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

## Git

Git is shipped with [Xcode](#xcode) in MacOS.

```bash
# configuration:
git config --global user.name "your_username"
git config --global user.email your_email@example.com
```

## GitHub

### GitHub with HTTPS & PAT

Note that GitHub no longer supports password authentication since 2021. To perform `git clone` with GitHub, use PATs (Personal Access Tokens) instead.

### GitHub with SSH

Ensure that your SSH key is created with the correct email. See [section on SSH](#ssh) and copy the entire content of the `~/.ssh/id_ed25519.pub` file from the last step.

Go to <https://github.com/settings/keys>, create a new SSH key and paste the contents from the previous step.

To use git with any (permitted) repositories, use the URL for `Clone with SSH`.

If you have already cloned with HTTPS:

```zsh
cd ~/<project directory>
git remote set-url origin <URL>
```

## VS Code

Install via official `.app` file (see [docs](https://code.visualstudio.com/docs/setup/mac)).

To launch VS Code from MacOS terminal, open VS Code Command Palette `Cmd+Shift+P` and type `shell command` to install `code` command in `$PATH`.

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
