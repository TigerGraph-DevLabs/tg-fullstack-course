---
template: overrides/main.html
---

Now that we have covered the high-level design of the application, we are ready to set up our local development environment and start creating our TigerGraph Fullstack App.

In this tutorial, we will use macOS. However, nearly every code section has Windows equivalents and Linux equivalents. For Windows reference, check out [this page](https://docs.microsoft.com/en-us/windows/wsl/install-win10)!

## Trusted Resources

Before beginning, it’s important to choose reliable sources to learn from. Just like it's important to get your news from reputable sources, it's important to get your technical information from tried and trusted sources. Here are some of our personal favorites:

## Tools

???+ tip "The HTML/CSS/JS"

    For anything to do with HTML, CSS, or JavaScript, [Mozilla's MDN](https://developer.mozilla.org/en-US/) is our go-to. We literally have it open all the time 😅.It's a good idea to head directly to [MDN’s GitHub](https://github.com/mdn/) page or their official documentation. It's best to head straight to the source. In this case, we will be using framework libraries like ReactJS and Antv G6.

???+ tip "The Browser"

    Our recommendation is Chrome. The extension tools are amazing and the team behind them are amazing too. We will use the JSON Formatter extension as well.It can be installed via the following [hyperlink](https://chrome.google.com/webstore/detail/json-formatter/bcjindcccaagfpapjjmafapmmgkkhgoa?hl=en).

???+ tip "The Editor"

    Our recommendation is Visual Studio Code. It's free, open-source, and works well on Mac, Linux, and Windows. Perhaps one of the best features of VSCode is it has a huge amount of [available plugins](https://aka.ms/vscode-marketplace) to choose from. Feel free to take a look!

    If you're not feeling VSCode, two other editors that are similar in their offering are [Sublime Text 3](https://www.sublimetext.com/) and [Atom](https://atom.io/). Both are great tools! Both are free to download. However, Sublime requires a subscription basis of $65 in order to gain business licenses.

    If you want a more complete offering, you may investigate using an integrated development environment (commonly called an IDE.) The reigning, best IDE for front-end development is [WebStorm](https://www.jetbrains.com/webstorm/). WebStorm is a very powerful IDE that has a lot of features and tools built into it. It aims to be more than just an editor; it aims to be the entire development suite. Great tool!

???+ tip "The Terminal"

    You will have to use a terminal, but it’s less scary than it seems, we promise! For the shell, we are going to use [bash](https://www.gnu.org/software/bash/). You don't need to install it unless you're using Windows (then use [these steps](https://docs.microsoft.com/en-us/windows/wsl/install-win10) to enable it). It's 99% already there on your computer unless you're using some obscure flavor of Linux. Whenever you open your Mac terminal, it'll be running bash by default unless it has been changed. To remedy any command, check out this [hyperlink!](https://explainshell.com/)

    However, there are other options as well. The reason we use bash is that it is so prevalent. Bash is everywhere. Everything you Google will have the answers written in bash. Other shell people swear by is [zsh](http://www.zsh.org/). All very cool but we  recommend looking at them later.

???+ tip "Node.js"

    Node.js is a runtime built on top of Chrome's V8. It allows you to develop apps in JavaScript outside of the browser. It's single-threaded non-blocking and asynchronous. This is achieved by the use of an event loop at the core of Node.js. If you know JS then you already know how to develop with Node.js! Let’s take a closer look...

    **For Windows**

    If you're running Windows and not using Windows Subsystem Linux (WSL), I recommend you use the [official installer](https://nodejs.org/en/) from the Node.js site. Make sure to choose the latest LTS version.

    **For Non-Windows**

    If you're not on Windows or you are using WSL, we recommend installing Node.js with [NVM (node version manager)](https://github.com/nvm-sh/nvm). NVM allows you to install many versions of Node.js at once and switch whenever you may need to. Additionally, NVM installs Node.js in a folder that will not have permission errors that you would otherwise run into with the official installer. Once you have nvm installed, you need to install a Node version. You can download the latest LTS version with this command.

    ```
    nvm install --lts
    ```
