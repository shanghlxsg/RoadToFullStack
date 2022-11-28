# Creating React Applications

## Setup Node Managers

[For macOS](/1-setup-and-overview/1b-macos/2-node-managers.md).

## Create React App

[Source](https://github.com/facebook/create-react-app).

```zsh
npx create-react-app my-react-app --template typescript --verbose
cd my-react-app

# install dependencies:
npm install axios

# run app in dev mode:
npm start

# run test watcher in interactive mode:
npm test

# build app for production to the build folder:
npm run build
```

### Folder Structure

#### Root Folder

[Reference](https://github.com/airbnb/javascript/tree/master/react#naming) for naming convention.

Once the project folder is created using `npx create-react-app`, the basic folder structure will look like:

```zsh
project-folder
├── README.md
├── package-lock.json # version control for all packages/dependencies
├── package.json # installed dependencies and default/user-defined scripts
├── tsconfig.json # root files and compiler options for .ts(x) files
├── .gitignore # configure files to be ignored by git
├── docs # for documentation notes (not auto-generated)
├── node_modules # where node packages are installed (by default included in .gitignore)
├── public # files not processed by webpack
└── src # where the magic happens
```

#### Public Folder

```zsh
public
├── favicon.ico
├── index.html # primary HTML file of the web app, only uses assets from `public`, calls root element from `src`.
├── logo192.png
├── logo512.png
├── manifest.json # information about the web app (mostly for mobile apps)
└── robots.txt # SEO configuration
```

#### Source `src` Folder

```zsh
src # where the magic happens
├── App.css
├── App.test.tsx
├── App.tsx # React entry point (calls React components)
├── index.css
├── index.tsx # javascript entry point (calls React <App />)
├── logo.svg
├── react-app-env.d.ts
├── reportWebVitals.ts
└── setupTests.ts
```
