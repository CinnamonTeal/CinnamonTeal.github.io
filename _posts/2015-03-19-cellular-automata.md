---
layout: post
title: Cellular Automata
---

![Alt rules](http://uncomp.uwe.ac.uk/wuensche/gallery/f_k5_examples.gif)

One of the most beautiful and fascinating concepts I have ever seen in my life: Cellular Automata. Available definitions are pretty dense and dry, but roughly speaking, celluar automata are repeating patterns that are created by individual cells which propagate according to very simple rules. Commonly each cell be in only one of two states (on or off, 1 or 0), but other patterns can be made by increasing the number of possible states for each cell (like a color, for example) The rules describe how the cell should propagate depending on its relationship to its neighbors.

The history is interesting and important, but read it on [Wikipedia:](https://en.wikipedia.org/wiki/Cellular_automaton) because I'm not interested in covering that here.

[Stephen Wolfram](https://www.youtube.com/watch?v=_eC14GonZnU) wrote an amazingly comprehensive book covering this topic called "A New Kind of Science," which he says took 10 years to write. You can [read it](https://www.wolframscience.com/) online for free.


<!-- explain the rules and how they work, with pictures -->
<!-- link to the wolfram youtube video -->
<!-- talk about applications for fluid dynamics etc -->



What I love about this, is how complexity emerges from a set of simple rules. It reminds me of what a seemingly deterministic yet simultaneously random universe we live in. The behavior of cellular automata are useful models of so many natural phenomena, such as the inherent randomness in fluid dynamics or the organic development of an entity as complex as a human being from a set of simple instructions like DNA. So we can study these patterns to try and learn about how complex structures emerge in nature. 

Let me explain the rules. I am going to go fast because this is a blog post, but if you want to take the time to really grok this check out [Wolfram Mathworld](http://mathworld.wolfram.com/ElementaryCellularAutomaton.html).

A one-dimensonal (or Elementary) automaton is the simplest kind of cellular automaton. The rules look like this:

![alt 1d](http://mathworld.wolfram.com/images/eps-gif/ElementaryCA30Rules_750.gif)

In this case the cells can only be 1 or 0, and each next generation changes based on the rules described in the image above. What happens when you repeat this pattern for severl generations is you eventually get an image that looks like this:

![alt rule](http://mathworld.wolfram.com/images/eps-gif/ElementaryCA30_1000.gif)

So far this isn't particularly amazing. If we program a cell with simple rules, we would expect to see regular and predictable behavior, like the above pattern. But we can study the behavior of these automata even further. What if we change the rules a bit? After 10 generations, nothing spectacular happens, but what if we run the experiment 100 generations, or 1000 generations? 

Stephen Wolfram did exactly that in the 80's and 90's. He suspected that the types of rules that can be embodied in computer programs, might actually be the types of rules that govern nature. So he systematically ran an experiment on all 256 possible simplest cellular automaton rules to see what would happen.

Here are some of the patterns that emerge:

![alt rules](http://mathworld.wolfram.com/images/eps-gif/ElementaryCA1_900.gif)

Pay close attention to Rule #30. Here it is close up:

![alt rule30](http://mathworld.wolfram.com/images/gifs/Rule30Big.jpg)

What is the pattern that you see here? If you look on the left side of rule number 30 there appears to be some consistent structures, but in the center and towards the right it appears actually very random. And it is. There is something about rule 30 that produces inherent randomness. And rule 30 isn't the only one. Check out rule 110:

![alt rule110](http://nicholasyager.com/assets/2014-04-29/rule110.png)

The implications of this are monumental. What can we infer from these structures about the basic principles of nature? Ordinarily we would think that something very complex must also at its root be very very complex, but what this shows us is that we can get extremely complex structures or behavior from even the simplest of rules. Maybe this helps us to explain how human beings can appear to have free will; they behave in seemingly random and chaotic ways, even though we know that we are bound by the physical laws of the universe. Without having seen the emergence of such complex randomness from cellular automata, one might be tempted to explain free will as evidence for some sort of a god. But once you see how enormous complexity can emerge in nature from such a simple set of rules, it almost seems inevitable that we would witness the types of randomness and chaotic behaviors in our universe, including random turbulence in fluid systems and the decision making processes of the brain. 

Remember that these particular cellular automata are the simplest kind. What if we add new dimensions? We can add color, or use algorithms such as k-nearest neighbors in a two-dimensional field. The most famous example of this is Conway's "Game of Life" discovered by J. H. Conway in 1970. It is a [totalistic cellular automaton](http://mathworld.wolfram.com/TotalisticCellularAutomaton.html), with a [Moore neighborhood range](http://mathworld.wolfram.com/MooreNeighborhood.html) of 1:

![alt gameoflife](http://mathworld.wolfram.com/images/gifs/puffertr.gif)   ![alt life](http://img.sadistic.pl/pics/fafe1da85d06.gif)

And we can try changing the rules even more. Take a [Turing Machine](https://en.wikipedia.org/wiki/Turing_machine) for example:

![alt turing](http://mathworld.wolfram.com/images/eps-gif/BusyBeaverS_901.gif) 

In the above example, only one cell gets updated each generation, rather that the multiple cells of the previous examples. But even in a simpler system which mimics a Turing Machine, randomness naturally emerges.

![alt turing2](https://ccrma.stanford.edu/~jieun5/coursework/220b/final-proj_html_5bcab052.jpg)

Examples of this are everywhere:

![alt examples2](http://pentadecathlon.com/lifeNews/2011/02/2011-02-16-c12-SC-exploded.PNG)

![alt examples](http://blog.stephenwolfram.com/data/uploads/2013/03/slide_012.png)

![alt examples3](http://rendell-attic.org/gol/turing_js_r.gif)

Not simply in computing simulations, but even (or perhaps especially) in nature. 

![alt bismuth](http://www.bismuthcrystal.com/n23-566d.jpg)

![alt shells](http://www.aimfeld.ch/cellmorphs/img/shells1.jpg)

![alt snowflake](http://ca.olin.edu/2005/cellular_automata/crystalization_example.gif)

Ultimately the trend is the same: we can produce surprisingly complex structures from very simple rules.

<!-- 
http://mathworld.wolfram.com/CellularAutomaton.html

http://www.mirekw.com/ca/rullex_1dbi.html -->

![Alt golly](http://golly.sourceforge.net/ticker.gif)


<!-- 
images: 
http://www.kamend.com/wp-content/uploads/WolframCA_Rule101.png
http://www.mirekw.com/ca/rules/1dto_marvel.gif
http://www.harrisondigitalmedia.com/forumPix/CellularAutomata.jpg
http://www.mirekw.com/ca/rules/1dto_class4a.gif
http://www.mirekw.com/ca/rules/1dbi_chaoticgliders.gif -->