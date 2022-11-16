# Setup Guide

## nvm (node version manager)

*Warning (1 of 2)! For Mac computers with Apple silicon, you need to run `nvm` in a shell that is running Rosetta.*

*Warning (2 of 2)! `node 18` will fail to run `create-react-app`. use `node 16` instead.*

```zsh
# install
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.2/install.sh | bash

source ~/.zshrc # same as closing and opening a new terminal
command -v nvm # correct installation returns `nvm`

# install node 16
# reminder - node 18 will fail to create react app on M1 Mac
nvm install 16

# check current version
node -v # or
nvm ls # detailed version report

# check all available versions
nvm ls-remote

# change node version
nvm use 16

# set default node version
nvm alias default 16
```

## npm (node pacakge manager)

`npm` is usually installed together with `nvm`. There is no need to upgrade/downgrade unless there are `npm` package dependency issues.

```zsh
# check version
npm -v # node 16 and 18 comes with npm 8.19.2

# (optional)
# update to 8.19.3 (legacy)
npm install -g npm@8
```
