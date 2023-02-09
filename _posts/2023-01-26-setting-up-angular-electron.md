---
layout: post
title: Setting up Angular + Electron
date: '2023-01-26'
published: true
---

# Angular and Electron

As of writing this, I am in my senior year of college. I have a capstone class where we work on a project to prove my abilities once I leave college. The project I am working on is going to streamline a video creation process. 

While a few years of college and tinkering have taught me how to make technical programs, I never worked with UI/UX much. It has been a daunting skill to learn as I switched between languages every year for different classes and project. But to simplify the UI/UX process, I decided that my dev stack was going to be Angular + Electron. This will allow me to focus on the design aspect of the GUI without worrying about the technical aspects. And it also allows me to develop an app for both the web and desktop without having to build two separate apps for one program. 

**THIS GUIDE IS FOR AngularCLI. NOT AngularJS!**

## Installing NodeJS

Get the NodeJS installer from here [NodeJS](https://nodejs.org/en/). Finish this step before moving forward.

## Installing TypeScript

TypeScript is installed from Node's package manager NPM:

**Global install**
```console
npm i -g typescript
```

## Installing Angular

There are two versions of Angular:
* AngularJS
* AngularCLI

AngularJS has been discontinued since the end of 2021. Starting 2022, there is now AngularCLI, which has been coded in TypeScript rather than JavaScript.

**Global Install**
```console
npm i -g @angular/cli
```

## Angular Project Setup

Before making a new project, the directory path for your project. Do not make the directory for the project. Instead, direct a terminal to the root directory that your project folder is contained in.

For example:
* **Project Directory** = ./Documents/Projects/HelloAngular/
* **Root Directory** = ./Documents/Projects/

Direct a terminal to the root directory and then run this command to create a new angular project:

```console
ng new HelloAngular
```

The terminal may ask about google analaytics if this is your first time using angular. That is your choice, but I haven't set that up before and don't intend to.

Then, the terminal will ask: `Would you like to add Angular routing? (y/N)`<br>
While it is not necessary, this enable multipage programs using a routing api. I always enable it and ignore it if I don't need it. 

And finally, the terminal will ask: `Which stylesheet format would you like to use?` I recommend using scss or sass.

At this point, a project folder named **HelloAngular** will have been made, git will be initialized inside the project folder, and you will be given a basic Angular app.

In your terminal, change directory into the project folder and you can test the project by running:
```console
npm run start
```
This will start a web service running on your computer that you can direct your browser at and see. The standard url will https://localhost:4200. Use Ctrl+C to stop the web service. 

## Electron Setup

Install electron by running this command inside the project folder:

*Note: this installs electron in only this project*
```console
npm i electron --save-dev
```

### Package.json

In the package root, open `package.json`. The start of your file will look like this:

```json
"name": "feral",
  "version": "0.0.0",
  "scripts": {
    "ng": "ng",
    "start": "ng serve",
    "build": "ng build",
    "watch": "ng build --watch --configuration development",
    "test": "ng test"
  },
```

Add `"main": "main.js"` to the root structure and `"electron": "ng build && electron ."` to the script structure. It should now look like this:

```json
"name": "feral",
  "version": "0.0.0",
  "main": "main.js",
  "scripts": {
    "ng": "ng",
    "start": "ng serve",
    "build": "ng build",
    "watch": "ng build --watch --configuration development",
    "test": "ng test",
    "electron": "ng build && electron ."
  },
```
### Main.js

In your project root, create a file called `main.js`. Copy this code into your file:

```javascript
const { app, BrowserWindow } = require('electron')

const createWindow = () => {
  const win = new BrowserWindow({
    width: 800,
    height: 600
  })

  win.loadFile('dist/feral/index.html')
}

app.whenReady().then(() => {
  createWindow()
})
```

### Index.html

From your project root, open `./src/index.html` and change the tag `<base href="/">` TO `<base href="./">`.

### Test Run

In your terminal that is directed at the project root, run:
```console
npm run electron
```

This will build the Angular app from before inside a desktop window.

## Where To Go Now?

`./src/app/app.component.html` holds the source page for the App. You can delete everything and start building from there (if you have routing enabled, delete everything except the routing tag at the end of the file). As I am learning Angular right now, I recommend you find a tutorial for angular that has been released after January of 2022.

**Good luck!**




