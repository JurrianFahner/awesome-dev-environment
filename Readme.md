> **`Info`** <br />
> This readme is optimized to be rendered on dark mode in Github.
> So if you want to have the best experience, you can [switch the dark mode on][github-darkmode].

# my development setup
This development setup is a very opinionated view with a lot of opinions and unsupported claims. 
Feel free to raise an issue if you want to provide alternative perspectives. 
But maybe you find here tools that you are not aware of and would like to explore... 
If you use a tool that needs to be added to my development setup, please create a PR. 😉 

## jetbrains IDE

JetBrains has beautiful integrated development environments (IDE) that you can use to build nice products. 
At first they might be a bit overwhelming, but after a while you will learn all bells and whistles (just take your time). If you are a  [polyglot programmer][polyglot-programmer], then it can be helpful to have a consistent experience with [fixed general keyboard shortcuts][shortcuts-intellij].

The following IDE are great for specific tasks:

| icon               | languages               | download link                 |
|--------------------|-------------------------|-------------------------------|
| ![][logo-clion]    | c / c++ / rust          | [download][download-clion]    |
| ![][logo-rider]    | c#                      | [download][download-rider]    |
| ![][logo-intellij] | java                    | [download][download-intellij] |
| ![][logo-pycharm]  | python                  | [download][download-pycharm]  |
| ![][logo-webstorm] | javascript / typescript | [download][download-webstorm] |

The community versions are more basic than the ultimate versions. The ultimate versions unlock for example also 
simple integration with all kind of frameworks. 

How to choose the right IDE for your job. That's actually very simple. You take the project and if it holds for instance mainly
java files, then you would opt for Intellij. If you need also typescript support for a small part in that code base, then 
Intellij can be extended by plugins to unlock also support for typescript. It is up to your preference how you want to use the
Jetbrains IDE, the rationale is that the IDE will adapt to you as a developer (see also [Fleet](https://www.jetbrains.com/fleet/) 
it shows how Jetbrains see their role to support the developer). 

## visual studio code
<img src="./img/vscode.svg" align="left" height="90em" />
This tool from Microsoft can be the swiss army knife for a developer. It can be used as a text editor, but can also be scaled up to a fully-fledged IDE. It just depends on your preference. 

I refrain myself to install too many modules, so it doesn't slow down. I commonly use it as a text editor on steroids.
It is also a great IDE for developing powershell scripts. 

[installation instructions](https://apps.microsoft.com/store/detail/XP9KHM4BK9FZ7Q) | [documentation](https://code.visualstudio.com/docs) | [sources](https://github.com/microsoft/vscode)

## java
<img src="./img/java-logo.png" align="left" height="90em" />
When you are building software with the programming language Java. There are a lot of options to choose from, see for example the list on java 21: https://foojay.io/almanac/java-21/ 

Be careful with the Oracle Java. This distribution is not allowed to be used freely and licences can be expensive. 

My general advice would be to use [Eclipse Temurin](https://adoptium.net/).

## windows terminal
<img src="./img/terminal.svg" align="left" height="90em" />
While working as a developer you often would like to have access to the commandline. For Windows users Microsoft has developed a great terminal to work with. Windows 11 has windows terminal installed by default. But for windows 10 you need to install it yourself. 

[installation instructions](https://www.microsoft.com/store/productId/9N0DX20HK701) | [documentation](https://learn.microsoft.com/en-us/windows/terminal/) | [sources](https://github.com/microsoft/terminal)

## wsl - windows subsystem for linux
<img src="./img/wsl-logo.png" align="left" height="90em" />
If you write software for linux on a windows pc, then you might want to have access to linux as well. On windows there is a tool called wsl2 with great integration into the windows operating system. 

[installation instructions](https://learn.microsoft.com/en-us/windows/wsl/install) | [documentation](https://learn.microsoft.com/en-us/windows/wsl/)

## linux distro
<img src="./img/ubuntu-windows-store.png" align="left" height="90em" />
For years I've used ubuntu as a desktop operating system to do all of my work. That originates from the time when windows blue
screens were very frequent and I decided to use something more stable. I started with linux from scratch, even tried mandrake etc.
Used also Fedora for a while. But when ubuntu decided to focus on a stable desktop I switched after a lot of distro hopping to 
make ubuntu my default desktop. 
When I need to choose between distros for server use, I think that RedHat Linux and Ubuntu Server are the best choices to make. 
But my personal favorite would be Ubuntu Server at the moment. 

Canonical and Microsoft are working together to improve the usability linux on windows, which resulted in wsl2.
So I think it might be also a good bet for the longer run. 

To install ubuntu in wsl, please go to windows store and search for ubuntu. 

## version control - git
<img src="./img/git-logo.png" align="left" height="90em" />
Git is the first choice for me when selecting a version control system.

Make sure that autocrlf is switched to false. Otherwise bash scripts or linux configuration can break, see also [this article](https://www.aleksandrhovhannisyan.com/blog/crlf-vs-lf-normalizing-line-endings-in-git/). Copy-paste
the following snippet to your terminal to make it happen. 

```shell
git config --global core.autocrlf false
```

When you want to list all configuration:

```shell
git config --global -l
```

[installation instructions](https://git-scm.com/downloads) | [documentation](https://git-scm.com/doc) | [sources](https://github.com/git/git) 

## containers and images
<img src="./img/docker-logo.png" align="left" height="90em" />

For containers and the use of images [Docker](https://www.docker.com/) is currently the default. Please be aware that when 
using [Docker desktop](https://www.docker.com/products/docker-desktop/alternatives/) that for personal usage it is free 
of charge, but for large corporations Docker has a software license in place. 

There is a difference between [docker engine](https://docs.docker.com/engine/) (which is free to use by everyone) and [docker desktop](https://docs.docker.com/desktop/). Docker desktop makes it possible to install a kubernetes cluster on your dev machine with one press of a button.  

Because there are licencing issues with docker desktop I decided to move to a different desktop tool for integration within 
windows. I opted for [Podman desktop](https://podman-desktop.io/). [Rancher desktop](https://rancherdesktop.io/) is the other alternative, which 
I haven't used yet. 

There is an [excellent post](https://www.acorn.io/resources/blog/selecting-between-docker-desktop-rancher-desktop-and-podman-desktop) where these
different desktop tools are compared with each other.

## if you really want to use docker

After a few freezes of the docker desktop ui and initialization issues after a reboot, I decided to get rid of docker desktop and go for docker engine. The reasons for me are the following:
1. Docker desktop doesn't add a lot of value.
2. Windows 11 supports now systemd on wsl2, so there is one reason less to have Docker desktop installed.
3. Potential licencing issues.

My advice would be to install WSL and use docker from WSL (follow [these instructions](https://nickjanetakis.com/blog/install-docker-in-wsl-2-without-docker-desktop)), the reason is that docker is more or less a standard tool nowadays (although it is not my favorite from a security perspective).

After install instruction: 
```powershell
# run the command below to open the powershell startup script
notepad $profile   # you can also opt for any other text editor, like vim or code for example.
```
Copy paste the code below in the editor, save and close it.
```powershell
function docker()
{
	$allArgs = $PsBoundParameters.Values + $args
	& wsl docker $allArgs
}
```

After this setup, you should be able to invoke the following from powershell:
```powershell
docker run -it hello-world
```

**Note** Mounting volumes in powershell is not likely to work, but will work in wsl.

<img src="./img/podman-logo.svg" align="left" height="90em" />

[Podman](https://podman.io/) serves as an alternative for docker it is deamonless and it doesn't need to run as root, which
makes it a more secure alternative than docker.

## github vs gitlab
I use Github for publishing my code in public repos and to collaborate on opensource projects. 
For my personal projects I use Gitlab, because I'm able to run the builds on my personal laptop and it is easy to setup. 

## my prompt
<img src="./img/oh-my-posh-logo.svg" align="left" height="90em" />
The default prompt for powershell is a little bit basic. You might want to know on which branch you are when you are in a folder which is tracked by git. In this case I would recommend to install posh.

I use the `MesloGM Nerd Font Mono`, which renders the prompt quite nicely. You can download it from [github.com](https://github.com/ryanoasis/nerd-fonts/releases/download/v3.0.2/Meslo.zip)

Example on windows with powershell:

![Example on windows with powershell](img/oh-my-posh-powershell.png)

Example on wsl with bash:

![Example on wsl with bash](img/oh-my-posh-bash-wsl.png)

[installation instructions](https://ohmyposh.dev/docs/installation/windows) | [documentation](https://ohmyposh.dev/docs) | [sources](https://github.com/jandedobbeleer/oh-my-posh) 



<!--
[installation instructions]() | [documentation]() | [sources]() 
-->


[logo-clion]: ./img/CLion_icon.svg
[logo-intellij]: ./img/IntelliJ_IDEA_icon.svg
[logo-pycharm]: ./img/PyCharm_icon.svg
[logo-rider]: ./img/Rider_icon.svg
[logo-webstorm]: ./img/WebStorm_icon.svg

[download-clion]: https://www.jetbrains.com/clion/download/
[download-intellij]: https://www.jetbrains.com/idea/download/
[download-pycharm]: https://www.jetbrains.com/pycharm/download/
[download-rider]: https://www.jetbrains.com/rider/download/
[download-webstorm]: https://www.jetbrains.com/webstorm/download/

[shortcuts-intellij]: https://resources.jetbrains.com/storage/products/intellij-idea/docs/IntelliJIDEA_ReferenceCard.pdf

[github-darkmode]: https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-personal-account-settings/managing-your-theme-settings
[polyglot-programmer]: https://medium.com/@guestposts_92864/what-is-a-polyglot-programmer-and-why-you-should-become-one-e5629bf720c2