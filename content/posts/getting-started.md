+++
title = 'Getting Started'
date = 2024-06-23T15:13:53+01:00
author = 'cosycodes'
draft = true
+++

# Introduction

Welcome to Cosy Codes, I'm Megan, owner of this blog. I created Cosy Codes as a way for me to practice my engineering skills, learn a few new things, and share that knowledge with others in a way that is approachable and fun. 

![Selfie of a woman with long, dark hair, dark green thick-rimmed glasses and a silver septum ring. She is wearing a black tshirt.](/images/selfie.jpg)

I'll share a bit more of my own journey later on, but for now let's get started with how you can also start building your own blog using [Hugo]. Hugo is an open-source framework for building fast and flexible static websites.  

# Getting Started

As I'm also starting out, I felt a static website would be a good start as I don't need a lot of dynamic content and there were also a number of pre-built [themes] available, which save me having to create all the front-end HTML/CSS content for the site. 

For the initial setup of the blog, I followed the [Hugo Quick Start guide][quickstart]. 

As I dug through the Hugo documentation, I was looking for what I would get needed to start: 

## Pre-requisites: 
1) If you don't have an integrated developer environment (IDE) or lightweight client in which to write your code, I recommend doing so. There are a number of options out there. **VS Code** is the most popular, according to the [Stack Overflow Developer Survey][survey] (2023). However, other popular IDEs include: Visual Studio, Intellij IDEA, Notepad++, Vim, PyCharm, etc.
2) Install a package manager, common package managers are `Homebrew` (MacOS) or `Chocolately` (Windows) but I’ve also used `pip` and `pipenv` (both for Python packages). Having a package manager will make the installation and management of the various packages you require later on *easier*.  Other package managers are of course available. 😸
    - In this case I installed [`Chocolately`][chocolately], as I’ve used it before. 
    - Regardless of package manager, for any package you want to download and install, **_you should check into the security and integrity of the package being downloaded_**, ensuring you’re installing what you think you’re installing and not introducing security vulnerabilities to your systems or your application. For this reason, I recommend only downloading from reputable and recognised package registries, such as PyPi, npm, NuGet, Terraform, etc. 
3) Install [Git]. It’s needed for much of the functionality you need when working with Hugo, please go to the Hugo docs for additional details. 
4) Install [Go], as the language is commonly used when working with Hugo.
5) Install [Dart Sass], it’s used as part of transpiling, or converting, Sass to CSS. As I already had Chocolately installed it was as easy as running `choco install sass` in an command prompt (cmd) and answering `Y` to whether I want to run the related install scripts. 

## Install Hugo 
> While I just installed the pre-requisite packages I need from my command prompt, the Hugo install docs explicitly state not to use Command Prompt or Windows PowerShell. So before the next step, I opened up VS Code, started a new Terminal session (Terminal > New Terminal) and used powershell, though you can also use git bash, to run the remaining commands in the Hugo Quick Start tutorial. **_Whether or not you need to do this will depend on your operating system, so as always reference the Hugo docs if in doubt._** 

6) To install Hugo, again it is as easy as running `choco install hugo-extended` as I wanted to install the extended version. Here are a few reasons why you may want to use the [extended version]. Link is for Windows, but there are documents for installing on Linux, MacOS, and BSD derivatives. 

7) *(Optional)* I also chose to install [GitHub Desktop], as a graphical user interface (GUI) for Git and one I can use to easily connect with my GitHub.com account when I’m ready to push my local changes there. You can also choose to use `git` from the command line, so just choose which works best for you! 

## Additional files creation 
While I was at it, the project is now created and the files visible within VS Code, I created a short `README.md` and a [`.gitignore`][gitignore] file using a couple of GitHub’s examples for Go and Hugo for my repo, in following best practices. 
- The README.md normally provides a short description of your project, as well as any useful and relevant information that people may need or want to know about your repo, its purpose, and its use.  
- A .gitignore file is important to help ensure you are not committing any sensitive files to your repo. This is especially important if you sharing this repo publicly, such as on GitHub or GitLab, other source code managers are out there! 

## Next step: Installing a theme
While the tutorial docs utilise `Ananka`, I knew I wanted to use [`risotto`][risotto] 

> Before choosing how to install the theme, I also read a bit about the difference between running the theme as a [submodule] and as the maker of risotto recommends installing it directly vs as a submodule, due to “the difficulty of tracking a specific release” I downloaded it directly from [GitHub][risotto github] as a `.zip file` (Code > Local > Download ZIP) and extracted the files to my themes directory within my local project. (ex. `C:\Users\[username]\cosycodes\themes`) and then followed the instructions to update my `hugo.toml` configuration file to utilise the new theme. 

**Note:** I found I had to initially copy entire [example site config][example config] into my project's `hugo.toml` to get risotto to build without errors. I also think the first time by leaving `risotto-main` (the default name of the extracted folder) in place as a themes subdirectory, instead of changing it to `risotto`, created the errors vs the config file itself. 

I made a few minor amendments to my `hugo.toml` file to add a bit of my own information and remove some of the unnecessary bits such as some of the `params.socialLinks` I’m not ready to fully utilise yet. Then made sure to save any files I amended in VS Studio before running the `hugo server` command from within my terminal session. 

I tested it and YAY, it mostly looks good except why is there `$ echo $ LANG` near the bottom of my page. We’ll find out next time. 

![screenshot of initial Cosy Codes website](/images/firstpushpreview.png)


[Hugo]: https://gohugo.io/
[themes]: https://themes.gohugo.io/
[quickstart]: https://gohugo.io/getting-started/quick-start/
[survey]: https://survey.stackoverflow.co/2023/#technology
[chocolately]: https://docs.chocolatey.org/
[Git]: https://git-scm.com/
[Go]: https://go.dev/
[Dart Sass]: https://gohugo.io/hugo-pipes/transpile-sass-to-css/#dart-sass
[extended version]: https://gohugo.io/installation/windows/#editions
[GitHub Desktop]: https://desktop.github.com/
[gitignore]: https://docs.github.com/en/get-started/getting-started-with-git/ignoring-files
[risotto]: https://themes.gohugo.io/themes/risotto/
[submodule]: https://git-scm.com/book/en/v2/Git-Tools-Submodules
[risotto github]: https://github.com/joeroe/risotto
[example config]: https://github.com/joeroe/risotto/blob/main/exampleSite/config.toml