# Creating a React app

## Setup

[Source](https://github.com/nvm-sh/nvm#manual-upgrade).

```bash
# node version manager
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm
source ~/.bashrc

# update to latest node
nvm install node
```

## Create an app

[Source](https://github.com/facebook/create-react-app).

```bash
npx create-react-app my-app --template typescript
cd my-app

npm install axios

# run app in dev mode:
npm start

# run test watcher in interactive mode:
npm test

# build app for production to the build folder:
npm run build

# creates a directory called my-app inside the current working directory with the following directory tree:

my-app
├── README.md
├── node_modules
├── package.json
├── .gitignore
├── public
│   ├── favicon.ico
│   ├── index.html # page template
│   └── manifest.json
└── src
    ├── App.css
    ├── App.js
    ├── App.test.js
    ├── index.css
    ├── index.js # JavaScript entry point
    ├── logo.svg
    └── serviceWorker.js
    └── setupTests.js
```
