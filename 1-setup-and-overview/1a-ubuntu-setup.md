# Software setup

## SSH

Source: <https://docs.github.com/en/authentication/connecting-to-github-with-ssh/>

```bash
sudo apt install -y ssh
ls -al ~/.ssh
# expect no response

ssh-keygen -t ed25519 -C "your_email@example.com"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
cat ~/.ssh/id_ed25519.pub
```

## Git

```bash
sudo apt install -y git
git config --global user.name "your_username"
git config --global user.email your_email@example.com
```

## GitHub

### GitHub with HTTPS & PAT

Note that GitHub no longer supports password authentication since 2021. To perform `git clone` with GitHub, use PATs (Personal Access Tokens) instead.

### GitHub with SSH

Ensure that your SSH key is created with the correct email. See [section on SSH](0-0-ubuntu-setup.md#ssh) and copy the entire content of the `~/.ssh/id_ed25519.pub` file from the last step.

Go to <https://github.com/settings/keys>, create a new SSH key and paste the entirety of `~/.ssh/id_ed25519.pub` (see [section on SSH](0-0-ubuntu-setup.md#ssh)) and save.

To use git with any (permitted) repositories, use the URL for `Clone with SSH`.

If you have already cloned with HTTPS:

```bash
cd ~/<project directory>
git remote set-url origin <URL>
```

## Chrome

Source: <https://itsfoss.com/install-chrome-ubuntu/>

```bash
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo dpkg -i google-chrome-stable_current_amd64.deb
```

## VS Code

Source: <https://code.visualstudio.com/docs/setup/linux>

```bash
# download the .deb package from official website at <https://code.visualstudio.com/download>
sudo apt install ./<file>.deb

# dependencies
sudo apt install -y apt-transport-https
sudo apt update
sudo apt install -y \
    code \
    python3-venv

# SSH setup (see SSH section above)
# ensure that your SSH key is set to the correct email
```


## Virtual Machine - Oracle BM VirtualBox

```bash
sudo apt install -y \
    virtualbox \
    virtualbox-guest-x11
```

## Other Dependencies

```bash
sudo add-apt-repository multiverse

sudo apt update
sudo apt install -y \
    ubuntu-restricted-extras \
    net-tools \
    zip \
    unzip \
    chrome-gnome-shell \
    gnome-tweaks \
    gnome-shell-extensions \
    gettext \
    curl
sudo apt autoremove -y

sudo snap install postman

# Netspeed installation
# Firefox: https://addons.mozilla.org/en-US/firefox/addon/gnome-shell-integration/
# (or) Chrome: https://chrome.google.com/webstore/detail/gnome-shell-integration/gphhapmejobijbbhgpjhcjognlahblep?hl=en
# Netspeed gnome extension: https://extensions.gnome.org/extension/104/netspeed/
```
