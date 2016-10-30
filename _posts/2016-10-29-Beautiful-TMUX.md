---
layout: post
title: "Beautiful TMUX"
date: 2016-10-29
---
# Discovery of tmux 

In receiving a demo of a labmate's [Mico-arm](http://www.robotnik.eu/robotics-arms/kinova-mico-arm/) [ROS](http://wiki.ros.org/Robots/MICO)-based control code, he showed me the nifty tool [`tmux`](https://tmux.github.io/) that allows for quick and easy movement between terminal windows. It was beautiful, and I've since learned some of the powers it holds. 

# What is `tmux`? 

Tmux allows for us to quickly attach and detach to terminal sessions that can be project/contextually named. Thus, we can be working on several projects - like a homebrewing recipe generator, a human-robot-collaboration user experience improvement project, and a ranking project - without having three unique terminals running with important and easy-but-still-takes-effort-to-initialize python instances. Also, we can make it pretty. 

*image of pretty* 

In this post, I'll go through some initialization and troubleshooting fixes I went through to finally truly enjoy playing with the command line. Thanks to [Daniel Miessler](https://danielmiessler.com/study/tmux/#gs.gLmbnDs) and [Ham Vocke](http://www.hamvocke.com/blog/a-guide-to-customizing-your-tmux-conf/) for helping me get started. See their posts for more reasons to use `tmux` over alternatives. 

# Installation

Using Mac OSX El Capitan with [Homebrew](http://brew.sh/), do: 
```bash
$ brew install tmux
```

## Basics of `tmux` 

`tmux` allows us to develop personalized environments with multiple windows and each window separated into multiple panes. Sufficiently using `tmux` involves the mastery of only a few commands (Note : 

### Shortcut combo
`tmux` includes a handy shortcut that defaults to Ctrl+b. I have remapped this in my config file (detailed below) to be Ctrl+a. I have also [remapped](https://coderwall.com/p/cq_lkg/remapping-caps-lock-key-to-something-more-natural-on-mac-os-x) the Capslock key to act as Ctrl to make Ctrl+a super simple to combo. 

### Starting a new session
Create a new tmux instance named 'session-name'. Using only `tmux new` will work as well, but is not recommended as it gives unique number identifiers to the sessions, which isn't all that helpful. 
```bash
$ tmux new -s <session-name>
```

### Check on active sessions
To see which sessions exist, 
```bash
$ tmux ls
```

### Attaching to existing sessions
To go to your last session, 
```bash
$ tmux a
```
To go to a specific session, 
```bash
$ tmux a -t <session-name>
```

### Detaching from sessions 
To detach from the current session, 
```bash
$ tmux detach
```
or simply, `Ctrl+a d`. 

### Killing sessions 
To kill the current session, 
```bash
$ tmux kill-session
```
To kill all sessions, 
```bash
$ killall tmux
```

### Adding and renaming windows 
To add a new window, use `Ctrl+a c`.
To rename the current window, use `Ctrl+a ,`. 

### Adding panes to windows
To add horizontal panes, use `Ctrl+a -`.
To add vertical panies, use `Ctrl+a |`. 
(I remapped theses in my .tmux.conf from the respective defaults `Ctrl+a %` and `Ctrl+a "`) 

### Reload your config file 
To reload your config file, use `Ctrl+a r`. (This is a functionality added in .tmux.conf)

# Prettifying your workspace

### Step 1. Choose a nice Terminal color scheme
Open a terminal and go to Preferences

*preferences image* 

Which will open this window

*preferences window image*

If you already have some nice themes installed, awesome. Otherwise, check out these premade [themes](https://github.com/lysyi3m/osx-terminal-themes). To install them, click the clone or download button and download as zip. 
*clone or download image*
Then, go to your downloads, unzip the file, go to the schemes folder, right-click+open the theme you've eyed from examples shown on the github site and pass through the security warning to open a new terminal. Then go back to preferences and make it default. 

### Step 2. Open up and play with your config file
Open .tmux.conf from your home directory using your favorite text editor ([SublimeText3](https://www.sublimetext.com/) in this case), 
```bash
$ subl ~/.tmux.conf
```
There's probably some default stuff there. Without any remorse, delete it all and cackle. This config file adds a nice status bar with your id, ip, window names, session name, and time at the bottom along with some [colors](http://superuser.com/questions/285381/how-does-the-tmux-color-palette-work) that pleasantly go with my chalkboard default terminal theme. 

Of everything here, the most important line is: 
```
# allow access 
set-option -g default-command "reattach-to-user-namespace -l bash"
```
It requires that you first install `reattach-to-user-namespace`: 
```bash
$ brew install reattach-to-user-namespace
```
One problem I had with `tmux` is that it wouldn't allow me to open up files or folders using the `subl` command. This deals with `tmux` acting separate from the typical terminal bash shell ([mostly-relevant-to-this-issue](https://github.com/ChrisJohnsen/tmux-MacOSX-pasteboard)). This line fixes this issue (make sure to ```$ tmux kill-session``` and reopen your terminals before complaining about it not working). 

There's way more stuff to do with the .tmux.conf file, but this will be a nice, simple starting place. 
