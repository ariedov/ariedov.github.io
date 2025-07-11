---
title: "My Setup 2025"
date: 2025-07-11T20:42:18+03:00
draft: false
---

### The Journey

In the last year or so, under the influence of [some bloggers](https://www.youtube.com/@ThePrimeTimeagen) I have started learning vim motions. My primary editor of choise at the time were some JetBrains products + VsCode.

#### JetBrains 

JetBrains support for vim motions is extensive via the [ideavim](https://plugins.jetbrains.com/plugin/164-ideavim) plugin, which adds support for all the motions you would need and even provides a handy .ideavimrc config file to tinker with. With the power of that, one could map every IDE action into a vim key binding, and finally ~achieve enlightenment~ use the IDE without needing to ever touch the mouse.

Could that be achieved by actually learning the IDE keymaps? Yes. But where is the fun in that?!

#### VsCode

I did not really dabble much in VsCode support for vim motions, since JetBrains provided me with __most__ of what I needed, and even more. But it is there. Just install the plugin.

#### XCode

Kida has a vim motions support. Will it work? Kinda - the motions are implemented, you can yip and yap all you want, but there is basically no command support. `/` just opens Xcode default search. `:` can navigate you to a line, but nothing more. It sucks. Just like Xcode.

### Neovim

Yes. It had to lead to that. You don't know how to exit vim, I don't need to exit it. Need a file explorer - neovim has it. Editor - of course. Games to waste some time while the code is compiling - you got it. Damn, I write this article in Neovim!

It can be colorful, it can be plain. It can navigate you quickly and highlight all the brackets, or it can be functional and minimal. The plugin support is incredible, lua is easy enough. Finally you are the master of your editor, and not the other way around. I enjoy it quite a bit. I did not connect a debugger yet.

### Skethybar

As I improved my knowledge of the tools I use and some Hyprland videos recomended by Youtube, I wondered, can my setup look less like MacOS, and more like something actually cool. 
That's how I found [Sketchybar](https://felixkratz.github.io/SketchyBar/), a customizable toolbar for MacOS that is kind-of a replacement for the default one.

With the default toolbar I always encountered the problem of actually important icons being hidden behind the notorious Apple Notch, so I even bought [Bartender](https://www.macbartender.com/), a tool to organise the toolbar, and hide the unnecessary icons behind an ellipsis. It helped, but I kinda hated the concept. Sketchybar helps me just have the icons I want visible, and the icons I don't want - hidden. Which is perfect for me.

### Aerospace

With my system starting to look more like Hyprland, I wanted it to feel more like it too. So, again, after some Youtube driven learning, I ended up on [Aerospace](https://github.com/nikitabobko/AeroSpace), a tiling window manager for MacOS. It is a better Desktop replacement for Apple, with some cool tiling features, so I can have the windows in my workspace nicely organised.

Some might ask: "Why wouldn't you use the Desktops that Apple engineers put so much effort into and already built into your Operating Systam?". The answer is: because it has animations that I couldn't disable. It is super annoying. I hate waiting every time I switch to an app, or a workspace. I want them to just appear. Aerospace solves that for me.

### Raycast

[Raycast](https://www.raycast.com/) is the cornerstone of the setup. It replaces so much functionality of the operating system, and makes it so much more approachable. The extensions saved countless hours of searching for the right button in the right app, it's all just there! Tailscale, Aerospace, Todoist, Obsidian, Jira and so so much more just at the ends of the fingertips.

You can assign shortcuts to specific actions, or make them aliases for quick search. At this point I cannot imagine how I would interact with my operating system without it, Raycast have become an essential productivity tool for just having the OS out of the way and getting things done.

### Tmux

I use [Ghostty](https://ghostty.org/) as the terminal. It really doesn't matter, it's just my window into [TMUX](https://github.com/tmux/tmux). Tmux is my frontend, Tmux is my backend. I literally have services right now that are running on tmux and have been for the past few MONTHS!

Tmux help me keep stuff alive. It helps me quickly switch between projects. It helps me keep my workflow organised. It helps me stay in the flow for quickly bringing up a note, another terminal window, lazygit, even my dotfiles are always available by a quick keypress from tmux.

Tmux is the raycast of the terminal, you just have to configure it yourself.

### Starship

[Starship](https://starship.rs/) makes my shell pretty.
