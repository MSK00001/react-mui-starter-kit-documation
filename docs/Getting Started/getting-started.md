---
sidebar_position: 1
---

# Getting Started 

Create React App is an officially supported way to create single-page React applications. It offers a modern build setup with no configuration.
sss
## Quick Start

Create a new app using one of the following commands:

```bash

cd my-app
npm start
``` 



## Get Started Immediately

You don’t need to install or configure tools like webpack or Babel. They are preconfigured and hidden so that you can focus on the code.

Create a project, and you’re good to go.

## Creating an App
You’ll need to have Node >= 14 on your local development machine (but it’s not required on the server). You can use nvm (macOS/Linux) or nvm-windows to switch Node versions between different projects.

To create a new app, you may choose one of the following methods:

## npx

```bash
npx create-react-app my-app
``` 
(npx comes with npm 5.2+ and higher, see instructions for older npm versions)

## npm

```bash
npm init react-app my-app
```


## Selecting a package manager
When you create a new app, the CLI will use npm or Yarn to install dependencies, depending on which tool you use to run the  `create-react-app`. For example

```bash
# Run this to use npm
npx create-react-app my-app
# Or run this to use yarn
```

## Output
Running any of these commands will create a directory called `my-app` inside the current folder. Inside that directory, it will generate the initial project structure and install the transitive dependencies:

``` bash
my-app
├── README.md
├── node_modules
├── package.json
├── .gitignore
├── public
│   ├── favicon.ico
│   ├── index.html
│   ├── logo192.png
│   ├── logo512.png
│   ├── manifest.json
│   └── robots.txt
└── src
    ├── App.css
    ├── App.js
    ├── App.test.js
    ├── index.css
    ├── index.js
    ├── logo.svg
    ├── serviceWorker.js
    └── setupTests.js
```