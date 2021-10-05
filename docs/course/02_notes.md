---
template: overrides/main.html
---

# Chapter 02 - Environment Setup

## Introduction

Now that we have covered the high-level design of the application, we are ready to set up our local development environment and start creating our TigerGraph Fullstack App.

In this tutorial, we will use macOS. However, nearly every code section has Windows equivalents and Linux equivalents. For Windows reference, check out [this page](https://docs.microsoft.com/en-us/windows/wsl/install-win10)!

&nbsp; &nbsp;


## Trusted Tools

Before beginning, it’s important to choose reliable sources to learn from. Just like it's important to get your news from reputable sources, it's important to get your technical information from tried and trusted sources. Here are some of our personal favorites:


???+ tip "The HTML/CSS/JS"
    ### The HTML/CSS/JS

    For anything to do with HTML, CSS, or JavaScript, [Mozilla's MDN](https://developer.mozilla.org/en-US/) is our go-to. We literally have it open all the time 😅.It's a good idea to head directly to [MDN’s GitHub](https://github.com/mdn/) page or their official documentation. It's best to head straight to the source. In this case, we will be using framework libraries like VueJS, Quasar, and Apache Echarts.

???+ tip "The Browser"
    ### The Browser

    Our recommendation is Chrome. The extension tools are amazing and the team behind them are amazing too. We will use the Vue.js devtools extension as well.It can be installed via the following [hyperlink](https://chrome.google.com/webstore/detail/vuejs-devtools/ljjemllljcmogpfapbkkighbhhppjdbg?hl=en).


???+ tip "The Editor"
    ### The Editor

    Our recommendation is Visual Studio Code. It's free, open-source, and works well on Mac, Linux, and Windows. Perhaps one of the best features of VSCode is it has a huge amount of [available plugins](https://aka.ms/vscode-marketplace) to choose from. Feel free to take a look!

    If you're not feeling VSCode, two other editors that are similar in their offering are [Sublime Text 3](https://www.sublimetext.com/) and [Atom](https://atom.io/). Both are great tools! One of our developers used Sublime for a decade and still loves it. Another one of our developers enjoys Atom’s TeleType feature, which allows for real time coding collaboration. Both are free to download. However, Sublime requires a one-time payment of $99 in order to gain certain licenses.

    If you want a more complete offering, you may investigate using an integrated development environment (commonly called an IDE.) The reigning, best IDE for front-end development is [WebStorm](https://www.jetbrains.com/webstorm/). WebStorm is a very powerful IDE that has a lot of features and tools built into it. It aims to be more than just an editor; it aims to be the entire development suite. Great tool!


???+ tip "The Terminal"
    ### The Terminal

    You will have to use a terminal, but it’s less scary than it seems, we promise! For the shell, we are going to use [bash](https://www.gnu.org/software/bash/). You don't need to install it unless you're using Windows (then use [these steps](https://docs.microsoft.com/en-us/windows/wsl/install-win10) to enable it). It's 99% already there on your computer unless you're using some obscure flavor of Linux. Whenever you open your Mac terminal, it'll be running bash by default unless it has been changed. To remedy any command, check out this [hyperlink!](https://explainshell.com/)

    However, there are other options as well. The reason we use bash is that it is so prevalent. Bash is everywhere. Everything you Google will have the answers written in bash. One of our developer's favorite shells is actually [fish](https://fishshell.com/) but it's not very popular. Another shell people swear by is [zsh](http://www.zsh.org/). These are all very cool but we  recommend looking at them later.


???+ tip "Node.js"
    ### Node.js

    Node.js is a runtime built on top of Chrome's V8. It allows you to develop apps in JavaScript outside of the browser. It's single-threaded non-blocking and asynchronous. This is achieved by the use of an event loop at the core of Node.js. If you know JS then you already know how to develop with Node.js! Let’s take a closer look...

    **For Windows**

    If you're running Windows and not using Windows Subsystem Linux (WSL), I recommend you use the [official installer](https://nodejs.org/en/) from the Node.js site. Make sure to choose the latest LTS version.

    **For Non-Windows**

    If you're not on Windows or you are using WSL, we recommend installing Node.js with [NVM (node version manager)](https://github.com/nvm-sh/nvm). NVM allows you to install many versions of Node.js at once and switch whenever you may need to. Additionally, NVM installs Node.js in a folder that will not have permission errors that you would otherwise run into with the official installer. Once you have nvm installed, you need to install a Node version. You can download the latest LTS version with this command.

    ```
    nvm install --lts
    ```

???+ tip "Quasar CLI"
    ### Quasar CLI

    We selected Quasar as the  <font color='#DD6E0F'>frontend framework</font>, and it is an **open-source VueJS-based** framework for building apps, with a single codebase to build SPAs, SSR App, PWA, BEX, Mobile, and Multi-platform Desktop Apps. Therefore, Quasar CLI comes in handy because it helps to create projects and build developing projects.

    Here’s how to install it!

    > Make sure that you have Node >=12.22.1 and NPM >=6.14.12 installed on your machine.

    *WARNING: Do  <font color='#DD6E0F'>not use odd versions of Node</font> (i.e. 13, 15, etc). These versions are* ***not tested with Quasar*** *and often cause issues due to their experimental nature. We highly recommend always using the LTS version of Node.*

    ```
    # Node.js >=12.22.1 is required.

    $ yarn global add @quasar/cli
    # or
    $ npm install -g @quasar/cli
    ```


## Frontend

With the tool installed, we are now ready to <font color='#DD6E0F'>create a quasar project</font> folder! First, it’s good practice to create a bigger scope project folder named `tigergraph_fullstack`.

```
$ mkdir tigergraph_fullstack
$ cd tigergraph_full
```


Next, we create a project folder with Quasar CLI:

```
tigergraph_fullstack$ quasar create front
? Project name (internal usage for dev) front
? Project product name (must start with letter if building mobile apps) Quasar App
? Project description A Quasar Framework app
? Author
? Pick your CSS preprocessor: SCSS
? Check the features needed for your project: ESLint (recommended), Vuex, Axios
? Pick an ESLint preset: Standard
? Continue to install project dependencies after the project has been created? (recommended) NPM
```

Now, we can open our `tigergraph_fullstack` project with vscode and open the terminal inside vscode as well. This can be done with a shortcut: ctrl + \` (for windows) or cmd + \` (for mac)

&nbsp; &nbsp;

Without further ado, let’s start our quasar project!  

```
tigergraph_fullstack$ cd front
tigergraph_fullstack$ quasar dev

 App •  READY  • Compiled: "UI"

 » App dir........... /Users/username/Desktop/tigergraph_fullstack/front
 » App URL........... http://localhost:8080
                      http://192.168.50.45:8080
                      http://169.254.99.222:8080
                      http://192.168.2.1:8080
 » Dev mode.......... spa
 » Pkg quasar........ v2.0.4
 » Pkg @quasar/app... v3.1.0
 » Transpiled JS..... yes (Babel)

 App • Opening default browser at http://localhost:8080
```



With the above lines, we have created our frontend project folder named front, and we have also run the project by using the command “quasar dev” inside the project folder (front).

Now, we can use a browser to open the project with URL: http://localhost:8080

&nbsp; &nbsp;

Awesome! Next, we will use some libraries to add to our fullstack app, so let’s install them inside the quasar project folder (front). To do this, we can run the following.

```
tigergraph_fullstack/front$ npm i echarts
```

&nbsp; &nbsp;

Neat! Next up, let’s examine the middleware, an essential part of our project.


## Middleware

### pyTigerGraph
### FastAPI
