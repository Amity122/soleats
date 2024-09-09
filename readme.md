# Overview
1. Node.js Version
2. Ionic VueJs Setup
3. Converting Typescript to Javascript

## Pre-requisites
1. Node.js v20.17.0

# Node.js Version
1. You can download node.js the way you want through this link here: https://nodejs.org/en/download/package-manager
2. In your terminal, type in ```node -v``` to check the version of node.js that you're using.

# Ionic VueJs Setup
1. For Windows type ```npm install -g @ionic/cli@latest```. For Linux, type ```sudo npm install -g @ionic/cli@latest```
2. Type in ```ionic start```. Use the app creation wizard and you will be redirected to a new tab in the browser.
3. Fill out the following details:
    a. App Name: SolEats
    b. Pick a theme color: Lightish Red
    c. Icon: Shallow Pan of Food
    d. Layout: Menu
    e. Pick a framework, in this project, pick Vue.
4. Click Continue, you may be asked to login with different platforms.

# About Capacitor
Turns any web application into a Native Mobile for android and iOS which you can distribute to the app stores. Capacitor doesn't necessarily need Ionic, but you can use Capacitors in any web app.

# Converting Typescript to Javascript
Caution: Long Instructions up ahead <br>

These instructions were taken from the official IonicDocs, which you can visit here: https://ionicframework.com/docs/vue/quickstart#build-your-way-with-typescript-or-javascript

1. Since this project won't be using Typescripts, open the terminal and run the following command:
```npm uninstall --save typescript @types/jest @typescript-eslint/eslint-plugin @typescript-eslint/parser @vue/cli-plugin-typescript @vue/eslint-config-typescript vue-tsc``` to remove all typescript dependencies.
2. Change all .ts files to .js. In a blank Ionic Vue app, this should only be src/router/index.ts and src/main.ts. If you're using tests, also change the extension of files in the tests directory.
3. In index.html, change the imported script file from /src/main.ts to /src/main.js.
4. Remove @vue/typescript/recommended and @typescript-eslint/no-explicit-any: ‘off’, from .eslintrc.js.
5. Remove ArrayRouteRecordRaw and the import of RouteRecordRaw from src/router/index.js.
6. Delete the src/vite-env.d.ts file if it exists.
7. Remove lang="ts" from the script tags in any of your Vue components that have them. In a blank Ionic Vue app, this should only be src/App.vue and src/views/HomePage.vue.
8. Delete the tsconfig.json file.
9. In package.json, change the build script from "build": "vue-tsc && vite build" to "build": "vite build"
10. Install terser npm i -D terser.