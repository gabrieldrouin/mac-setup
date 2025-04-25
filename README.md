## My Mac Setup

A repository for all of my apps/tools/settings.
Inspired by CodingGarden's [mac-setup repo](https://github.com/CodingGarden/mac-setup/tree/main).

- [What Macbook do I have?](#what-macbook-do-i-have)
- [OS Settings](#os-settings)
  - [Desktop](#desktop)
  - [Finder](#finder)
  - [Dock](#dock)
- [Homebrew](#homebrew)
- [Raycast](#raycast)
  - [Homebrew Plugin](#homebrew-plugin)
  - [Window Management](#window-management)
- [Keyboard Customizer](#keyboard-customizer)
- [Battery](#battery)
- [App Switching](#app-switching)
- [Menu Bar Utilities](#menu-bar-utilities)
  - [Hidden Bar](#hidden-bar)
  - [System Stats Widgets](#system-stats-widgets)
- [Break Timer](#break-timer)
- [Docker](#docker)
- [Warp](#warp)
  - [Shell](#shell)
  - [Prompt](#prompt)
- [Dotfiles](#dotfiles)
- [Github SSH Setup](#github-ssh-setup)
- [Node.js](#nodejs)
- [Other Apps](#other-apps)

## What Macbook do I have?

I am using a [M3 Max 14-core CPU/30-core GPU/36GB RAM/1TB SSD 14-inch Macbook Pro](https://everymac.com/systems/apple/macbook_pro/specs/macbook-pro-m3-max-14-core-cpu-30-core-gpu-14-late-2023-specs.html) for personal and professional use.

## OS Settings

These are my preferred settings for `Desktop`, `Finder` and the `Dock`.

### Desktop

* System Preferences
  * Desktop & Dock
    * Desktop & Stage Manager
      * Show Items
        * On Desktop -> uncheck
        * In Stage Manager -> uncheck
      * Click wallpaper to reveal desktop -> Only in Stage Manager
      * Stage Manager -> uncheck
      * Widgets
        * On Desktop -> uncheck
        * In Stage Manager -> uncheck

I also prefer to set my wallpaper to plain black.

### Finder

* Finder -> Preferences
  * General -> Show these on the desktop -> Select None
      * I try to keep my desktop completely clean.
  * General -> New Finder windows show -> Home Folder
      * I prefer to see my home folder in each new finder window instead of recent documents
  * Advanced -> Show all filename extensions -> Yes
  * Advanced -> Show warning before changing an extension -> No
  * Advanced -> When performing a search -> Search the current folder
* View
  * Show Status Bar
  * Show Path Bar
  * Show Tab Bar

### Dock

* System Preferences
  * Desktop & Dock
    * Size -> Small as possible
    * Position on screen -> Left
    * Automatically hide and show the Dock -> Yes
    * Animate opening applications -> No
    * Show suggested and recent apps in the Dock -> No

### Other

* Keyboard
  * Keyboard Shortcuts
    * Function keys
      * Use F1, F2, etc. keys as standard function keys -> check

## Homebrew

[Homebrew](https://brew.sh/) allows us to install tools and apps from the command line. It's commonly known as the missing package manager for Mac OS.

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

This will also install the xcode build tools which is needed by many other developer tools.

After Homebrew is done installing, we will use it (via RayCast) to install everything else we need.

## Raycast

[RayCast](https://www.raycast.com/) replaces the built-in spotlight search and includes additional productivity features.

```sh
brew install raycast
```

### Homebrew Plugin

The [RayCast Homebrew Plugin](https://www.raycast.com/nhojb/brew) enables easy package installations directly from RayCast.

### Window Management

In Raycast's Settings -> Extensions -> Window Management -> Hotkeys, I select the "Rectangle" preset.

## Keyboard Customizer

[Karabiner-Elements](https://karabiner-elements.pqrs.org/) enables keyboard layout remappings. I use it so I can switch between my PC and Mac while keeping the same layout on my [Glove80 keyboard](https://www.moergo.com/).

```sh
brew install --cask karabiner-elements
```

## Battery 

[Aldente](https://apphousekitchen.com/) gives control over the charging behavior of Mac OS, helping extend battery lifespan and maintain peak performance.

```sh
brew install --cask aldente
```

## App Switching

[AltTab](https://alt-tab-macos.netlify.app/) enhances Mac OS' default `CMD+TAB` app switcher, most notably by showing full window previews.

```sh
brew install alt-tab
```

## Menu Bar Utilities

### Hidden Bar

If you have several apps running that have menu bar icons, [Hidden Bar](https://github.com/dwarvesf/hidden) will let you choose which ones should be hidden after a timeout. This cleans things up if you have a ton of background apps running.

```sh
brew install hiddenbar
```

### System Stats Widgets

[stats](https://github.com/exelban/stats) allows to see network traffic, CPU temp/usage and RAM usage from the menu bar.

```sh
brew install stats
```

## Break Timer

[Time Out](https://www.dejal.com/timeout/) enables automatic break reminders.

I have it setup to show:
* 10 second micro break every 15 minutes
* 1 minute long break every 60 minutes

## Docker

[Docker](https://www.docker.com/) is an open platform for developing, shipping, and running applications.

```sh
brew install --cask docker
```

## Warp

[Warp](https://on.warp.dev/home) is an AI-integrated terminal for natural language input, autofill, and intelligent suggestions.

```sh
brew install --cask warp
```

### Shell

[Oh My Zsh](https://ohmyz.sh/) is an open source, community-driven framework for configuration management of zsh, Mac OS' default [shell](https://en.wikipedia.org/wiki/Comparison_of_command_shells).

### Prompt

I use Warp's default prompt with [FireCode Nerd Font](https://www.nerdfonts.com/font-downloads). For additional shell customization, I recommend using [Starship](https://starship.rs/guide/).

## Dotfiles

All my dotfiles are stored on [github](https://github.com/gabrieldrouin/dotfiles).

I clone this repo to my machine and copy the files into my home directory.

## Github SSH Setup

* Follow [this guide](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) to setup an ssh key for github
* Follow [this guide](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account) to add the ssh key to your github account

## Node.js

[Node Version Manager](https://github.com/nvm-sh/nvm) is a POSIX-compliant bash script to manage multiple active node.js versions.

With nvm is installed, you can install a specific version of node.js and use it:

```sh
nvm install 22
nvm use 22
node --version
```

## Other Apps 

* [discord](https://discord.com/) - Messaging/Community
* [vlc](https://www.videolan.org/) - Video Player
* [figma](https://www.figma.com/) - Image editor
* [visual-studio-code](https://code.visualstudio.com/) - Code Editor
* [sublime-text](https://www.sublimetext.com/) - Text Editor

You can install them in one go by placing them all into a text file and then running this command:

```
discord
vlc
figma
visual-studio-code
sublime-text
```

```sh
xargs brew install < apps.txt
```
