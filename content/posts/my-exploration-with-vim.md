---
title: "My Exploration with VIM"
date: 2025-01-18
draft: false
categories: ["Coding", "Productivity"]
tags: ["vim", "neovim", "productivity", "linux", "editor"]
description: "VIM stands for Improved VI which is text editor used for writing code. My journey from VS Code to Neovim."
ShowToc: true
TocOpen: true
---

### Introduction

VIM stands for Improved VI which is text editor used for writing code, mostly used when we're actually writing code on server since we don't have privilege to work with fancy vs code on server so people forced to write some config file over there. But It's efficient way to write anything and it's keyboard driven workflow makes you fall in love with the I feel someone want premium writing experience on editor wherever on laptop, they should tried at least once. In my own words VIM is a language of keyboard there's a pattern in how keyboard is configured and VIM tell's you what's is that. Right now I'm writing in obsidian with vim binding enabled. So I bit I'm obsessed with this VIM.

### Why My interference with VIM

When I try anything to do with git it switched to vim mode, on server working at Arista, I compelled to use somewhat vim mode I feel irritated somewhat, such a ugly flow and escape button in the corner always not felt not natural to work with. But somehow I gave it a try with remapping the escape with the capslock. to extend the further experience I gave a try on visual studio code by enabling with vim extension and I somewhat liked it, but It's kind of constrained environment the feeling was missing something then somehow I jumped to Neovim, watched so many video, spent so much time Do I actually need it, but I tried and It felt like wow !!!

![VIM Meme](https://i.imgflip.com/abt2pv.jpg)

### It Changed Everything

So after then My life has been changed completely how I interact with computer, took one month to configure neovim workflow doing the companies work side by side felt a bit overwhelming but I endure the pain, learn some cool config setup developed my Personal development environment, Fall into love with some youtube channel like TJ'vries, and the ThePrimegen(Official advertiser of neovim, ex netfilx guy) and for that period my youtube recommendation filled with those video which gave me basic understanding of how a ide works, and I think I also got to know how the code is rendered behind the scenes in an ide, how the lsp(language server protocol), basics of linting and formatting, autocompeletion works and how we can import different lsp's for different languages, Mostly I don't believe in ricing everything, since I've so much experience with ricing cannot satisfy you as I've tried with the notion and obsidian, So I mostly followed what most people have already configured Initially I took help from the My college friend Ayush and with his basic setup I tried to understand everything and this comes very easy to me since I've that engineering mindset and I know that a good software how it feels, it doesn't feel unnecessary things, somewhat like writing a full proof things which pass all the test-cases what We've learnt from doing Codeforces and Now I've free heavy coding assistance support through Augment.

### VIM is everywhere

Apart from the neovim setup I've also added tmux support for the same to create and managing different terminal session, and I installed plugins from TPM(tmux plugin manager), I rice the tmux. I felt so in love with the vim, that I tried to find vim in everything, I tried yazi, ranger for the file manager and they are great, I also tried oil.nvim, yazi.nvim for neovim, for browser I've installed vimium extension and Now I tried to avoid so much mouse that whenever I felt use of mouse I tried to find alternative solution.

So My love for this keyboard driven setup doesn't end here, I basically changed the os of my own laptop entirely Now I've Omarchy installed in my macos, took a backup for the all the data I've in my laptop and remove all the, someway I felt like this

![OS Change Meme](https://i.imgflip.com/abt3jx.jpg)

### LSP's, TreeSitter

![LSP Meme](https://i.imgflip.com/abtaso.jpg)

After you try and feel vim, you find something is missing in the workflow, actually you've experience the autocompletion, going to variable definition, folding the code, but there's a plugin's for everything here. Now LSP's for particular language which are responsible for code auto completion it's is platform independent, Previously the editor have the proprietry inhouse LSP's now they are independent, you can build your own language and your own LSP's which is rpc json protocol So I come across a whole open source community spent a lot of time finding the suitable plugin for everything, I don't to worry about what you need about since you've experienced different editor like JET Brains IDE then you know how we can find the 'go to definition' feature in IDE and you end up hunting for that nvim plugin which satisfy your requirement so this things come naturally to you. But after configuring everything I got to know many things under the hood. If you've ever overwhelmed with the option's and keyboard shortcut provided by the vs code or maybe you want some ide which give you the recent opened or edited file with some easy keyboard shortcut. Believe me the keyboard shortcut I used in vim is completely different from what we've experience it comes very naturally to use, most of the task is done with the home row itself.

### Git workflow

Vim gives to power to work with buffer, instead of directly modifying the file you'll work with the buffer's, buffer's are the readed in memory files with :w command you write the actual file, it's very helpful you can actually stage/unstage the changes in the hunks / different sub-parts, viewing the diff and resolving the merge conflict very natural with this setup since git is also written by the guy which invented the linux, so they basically follow the same philosophy so you can feel once the power of VIM. I feel neogit is very awesome, I felt in love with that extension, I feels like AHA Moment for me working with that. And also you end up using the 26 x 26 combination of keyboard, and it'll give you smooth freedom to try each and everything you can expect. I was frustrated with opening the git locked file in vs code for recent files with git different. I believe the git workflow give me a closer to the neovim setup since most of the initial time spent at Arista is spent on learning git and it's advanced feature, I don't know a 4 year experience guy struggling with the Git at Arista with the lateral entry, Since most of the work done here is done on single branch and the main branch, I don't find the branching help much because a lot of time you've to time spent on the switching the branch so I learnt a lot ot advanced git features like gitworktree to escape from hassle of repeated doing things, I'm the first guy in the team which uses this feature of using the gitworktree, and a lot of configuration is missing for the repo setup which I took initiative to fix that. So my 80 % of time spent of the configuring these thing and rest 20 of the time spent on actual coding so My manager is actually not so happy why I'm taking too long to complete the task but once I started it took a while to understand but completed the tasks on time.

### CLI Tools

I also tried the AI CLI tools at Arista, So I completely changed myself into the vibe coder and once you understand the requirement with the powerful coding agents like Augment you can easily complete the tasks easily and smoothly. Personally I find opencode best for it if you're looking for opensource vs code like feel extension in you neovim workflow.

### Zathura

Apart from that I can't forgot to mention zathura which is vim based pdf viewer, I find it very much more powerful efficient than other pdf view since it does the job very rich sense and you can easily configure this using the zathurarc file how much you want to scroll at a time.

### Last Note

If you every have tried and felt not been comfortable with it you should remap the escape key with caps-lock and escape key. and feel the power of VIM

![VIM Power Meme](https://i.imgflip.com/abtbgh.jpg)

Thanks !!!

