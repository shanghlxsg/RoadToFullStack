# Creating React Applications

## Setup Node Managers

[For macOS](/1-setup-and-overview/1b-macos/2-node-managers.md).

## Create React App

[Source](https://github.com/facebook/create-react-app).

```bash
npx create-react-app my-app --template typescript
cd my-app

# install dependencies:
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
