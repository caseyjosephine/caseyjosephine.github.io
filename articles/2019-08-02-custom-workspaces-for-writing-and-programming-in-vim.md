---
layout: page
title:  "Here's how to create custom workspaces to switch between programming and writing prose in Vim"
date: 2019-08-02
permalink: /custom-workspaces-for-writing-and-coding-in-vim/
---
Writing prose and programming are two fundamentally different activities.

Vim is my favorite text editor. It has a steep learning curve, but once you learn the basics, editing becomes joyfully efficient. 

There's a reason why Vim is more popular among programmers than it is with writers: it's a command line tool that's not intuitive, and using it without frustration requires both technical competency and grit. 

If your average writer asked me "Hey, what software should I use to write my fantasy novel?" I would be unlikely to reply "You should totally use Vim."

*However*, I bet I'm not the only person who uses Vim on the daily and also writes prose. That's why I wanted to write a quick article on how I pimped my .vimrc to create custom workspaces for programming and writing that I can toggle on the fly.

This is what it looks like:

![Programming mode vs writing mode in Vim](/assets/images/vimmodes.png){: .img-fluid}

Here's how we do it.

## Make lines work like they do in other text editors

In programming, lines tend to be discrete entities. Sometimes, a line will contain so much information that it keeps going even past the visual end of the screen, and that's not a problem. 

Lots of people want to see the whole line on the screen, which we can do by adding this to .vimrc: 
  
`set linebreak`

This works by softwrapping, which inserts a visual line break but doesn't add an actual carriage return character. 

If you have this setting turned on, you've probably discovered that Vim ignores the visual linebreaks when you use `j` and `k` to move down or up a line, respectively.

This makes some sense when you're programming, but in prose it completely breaks things. If a prose writer keeps typing sentence after sentence without hitting return, that writer is probably writing a paragraph. If the writing is good, each word should matter. When we edit a paragraph, we want to be able to get to any part of the paragraph as quickly as possible. 

Vim's default behavior makes it hard to get to the middle of the paragraph, and while we could use `gj` and `gk` to jump by visual lines, this effectively doubles the number of keystrokes we need and that's no fun.

To fix it, we just need to remap `j` to `gj` and `k` to `gk`:

`nnoremap j gj
nnoremap k gk`

I universally want to move by visual line, so I've got this as a permanent setting in my .vimrc.

## Adding the Goyo plugin for distraction free writing

I try not to add many plugins to Vim, since most of the time Vim can already do what I need without the plugin (I usually just need to learn something new to make it happen). But I like the Goyo plugin for distraction free writing.

What's great about Goyo is that it gives your words room to breathe by increasing the padding in your window. It also eliminates the line numbers, which is nice for prose (it doesn't matter to me what paragraph number I'm working on when I'm writing, I just want to write).

[Goyo](https://github.com/junegunn/goyo.vim) is available on Github, and setting it up is straightforward: just grab the [vim-plug plugin manager](https://github.com/junegunn/vim-plug) from Github and read the instructions. Then add goyo to your .vimrc:

`call plug#begin()
Plug 'junegunn/goyo.vim'
call plug#end()`

After you install Goyo with a quick `:PlugInstall` you can toggle Goyo by typing `:Goyo` (to turn it on) or `:Goyo!` (to turn it off). It's a nice start for our writing mode, but we're not done yet.

## Thinking about what changes work best for your writing process

Here's the fun part: messing around until you figure out which settings mesh well with your workflow. My recommendation is to open up a markdown file and play around with settings in command mode until you get your editor looking the way you want it to. 

The important thing is to keep track of the settings you like, since we'll eventually create a custom command to toggle writing mode.

Vim setups are intensely personal, and my writing preferences aren't universal. But here's what I like.

**A light colorscheme.** Dark mode is my typical preference, but I make an exception for writing. My favorite lighter colorscheme is [Solarized](https://github.com/altercation/vim-colors-solarized), which is what I'm using for writing mode. 

When I tried to switch to Solarized on the fly by using `:colorscheme solarized` everything came out all wonky. That's because I didn't read the instructions well enough on Github and neglected to use a color palette that works within the terminal. Adding `let g:solarized_termcolors=256` to my .vimrc fixed the issue.

It's worth nothing that the settings in your GUI might not play nicely with terminal colorschemes, so if things look weird check your GUI settings first.

**Spell check.** I don't love Vim's spell check, but since I'm pretty decent at spelling it works okay for me. I mostly write in English, so I added the following to my .vimrc:

`set spelllang=en_us`

Turning on the spell check is a simple command `:setlocal spell`.

**Syntax highlighting**. One of the great things about writing in Markdown is that you don't need any formatting to make it readable. I like colors though, so bring on the syntax highlighting.

I would guess that most people have syntax highlighting turned on by default in their .vimrc file, like so:

`syntax enable`

Now we've figured out exactly what we need to turn on when we want to enter writing mode, and it's actually not much: just Goyo, the Solarized Light colorscheme, and spell check.

## Creating a custom command to toggle writing mode

We already know what commands we need to get Vim looking how we want it to look when we write, but for sure we're not going to just type those all out every time we write because the computer can do that for us.

What we want to do is open our .vimrc file and create a custom command that makes all the changes we want when we're writing. Here's what mine looks like:


`:command Writemode colorscheme solarized | setlocal spell | Goyo 70`

The first bit just tells Vim "Hey, this is a command." Writemode is the name of the command; you can name your command whatever you want, although Vim requires the first letter to be capitalized. Then I just string together the settings I want to toggle using pipes, which should be somewhat familiar to those who like bash scripting. In this case, the pipe isn't using the output of one command as input for the next; instead, it's just connecting them within a single command.

After I save my .vimrc, I can open any file in Vim and type `:Writemode` to make it look all writerly.

There's still one last step, though: we want to toggle our settings on the fly, and right now we have to exit Vim and then reopen it to get back to our default settings. That's not realistic, especially since it takes some people *years* to exit Vim.

We just need to come up with another custom command that undoes all the things we did: 

`:command Codemode colorscheme oceanlight | set nospell | Goyo!`

Tada! Now we can type `:Writemode` to enter our writing mode and `:Codemode` to get back to our default settings.

I hope this was helpful for all you programmers who like to write slash writers who like to program. Before I go, here's one final Vim tip for the road: in normal mode, g Ctrl-g will give you a quick word count.  

