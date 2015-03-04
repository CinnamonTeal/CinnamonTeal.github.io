---
layout: post
title: Change Your .bash_profile, Change Your Life
---

One of the the most helpful tools that I have are my tricked out .bash_profile and .bash_prompt. It really makes working in the shell a LOT easier (and more fun), and if you are still using the default terminal prompt, I invite you to upgrade. TL;DR, scroll to the bottom for the how-to guides.

As a beginning web developer, using the command line (aka terminal, aka bash) can be disorienting, more time consuming than it needs to be, and rough on the eyes. With a simple white background and black text, it can be difficult to quickly find the information you need when it all looks the same.

![Alt boring](img/change\ bash\ change\ life/boring.png)

Better would be to have a different colored background, with fonts in various colors to help us parse the different aspects of what we are looking at. The way to achieve this is to customize the file that bash uses to load your settings and preferences, which is called .bash_profile. The ‘.’ before the filename indicates that it is a hidden system file (in OSX), so if you don’t see it in your “home” directory (aka “~”), then copy and paste the following into Terminal:

{% highlight bash %}
$ defaults write com.apple.finder AppleShowAllFiles YES
{% endhighlight %}

Once you find .bash_profile, open it up in your favorite (Sublime) Text editor and check it out. It turns out that there is a special syntax that I suspect may be unique to bash, so changing these settings will not be immediately intuitive and is very likely to confuse the crap out of you. That’s fine, it’s not impossible. Aint nothin’ to it but to do it.

Beyond simply changing colors, you can also add functionality, which is a critical piece of why a customized .bash_prompt is such a helpful tool. For example in my bash prompt displays my machine name in one color, (so I don’t get confused if I am working on a remote machine), the working directory that I am currently in using a different color, and in yet a third color which branch of git I am working on (only while working with git). I never have to type “pwd” and almost never need “git branch.” Calling ls in bash displays file names in a different color from folder names, so I can easily differentiate between files and directories. These are just some examples. Your bash prompt is a highly personal configuration that will probably evolve as you develop your skills and an ever more intimate relationship with your machine.

I found the following online guides to be really helpful and you probably will too. Start [here](http://www.cyberciti.biz/tips/howto-linux-unix-bash-shell-setup-prompt.html), and [here too](http://cli.learncodethehardway.org/book/ex21.html) for a primer on what .bash_profile does and how it does it, and a natural segue leads to [this guide](http://www.cyberciti.biz/faq/bash-shell-change-the-color-of-my-shell-prompt-under-linux-or-unix/) about changing the colors in your bash prompt. Indispensible is this page of charts detailing the various bash [colors and formatting](http://misc.flogisoft.com/bash/tip_colors_and_formatting) control sequences (also [this one](http://www.logilab.org/blogentry/20255)). And if you get pissed off because it’s not working and you don’t know what to do, you might be able to figure out why at [this page](http://jakeboxer.com/blog/2011/11/06/bashs-ps1-syntax-the-inspiration-for-brainfuck/).