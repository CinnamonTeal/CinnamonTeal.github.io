---
layout: post
title: Much Binary! Very Hex! So CS! Wow!
---
![Alt cpu](/../img/cpu-die.jpg)

**3.11.15** 19:11

I want to talk about number systems. 

How do we get from code like ruby, to binary (1's and 0's), and why is *that* what the machine can understand? When we think of numbers, we usually think in the decimal system.
Decimal as in "deci-", meaning ten. This is why it is also called "base 10" - there are only ten characters we can use (0-9). We count from 0-9, and then the numeral characters repeat: 10, 11, 12...22...32...132... every time we get another ten. 

But why is this the number system we use? I actually don't know, but if I wanted to bullshit you I'd probably make something up about humans having 10 fingers... (hey, that might actually be why)! 

In reality, number systems are completely arbitrary. We could invent any number system we wanted to represent quantities. For example, the concept of the number 4 can be thought of in at least two different ways: there is the actual instance of there being 4 countable things, and then there is the incidental representation of that quantity, either with the Arabic numeral 4 (which most of the 'western' world uses today), with the Roman numeral IV, with the Hebraic numeral ד (pronounced "Dalet"), the Chinese numeral 四 ("sì", in Mandarin, or "sei" in Cantonese), or with whatever numeral you decide to invent to represent that.

So understanding that we can represent quantities with pretty much any arbitrary notation, we can explore two other number systems that matter for hackers: hexadecimal and binary. 

First, binary. It's important to keep in mind that no matter how smart computers may seem, they're really about as smart as a light switch. Literally. All it understands is "on/off." 1 is "on," 0 is "off." That's it. That's all there is to binary. It's called machine language, because it's what the machine can "understand." It's somewhat analogous to neurons firing in the brain or not. One can't look at a neuron firing and derive any meaning from it. The thing to recognize is that if you want to turn "on" and "off" into something that has meaning, then we need to create a system that can 'encode' meaning by leveraging the on/off states that the metal in a computer can understand. 

Random aside: things besides "on/off" can be thought of as binary, for example "true/false," "good/bad," "black/white," "gay/straight," "republican/democrat", "food/nonfood", "predator/nonpredator"... binaries are everywhere in the world, but there are often third options and gray areas that binary thinking [might overlook](http://thearchdruidreport.blogspot.com/2011/10/trouble-with-binary-thinking.html). So binary thinking is often limiting and overly reductionist in the real world, although in computing it's appropriate. ^_^

OK back to the binary number system. Binary (bi- meaning two, hence why it is also called a "base-2 number system") can only represent quantities using two symbols: 1 and 0. Therefore if we want the computer to understand the number 4, we have to represent that using only 1's and 0's, or on's and off's, kinda like Morse Code (but not really).

So how does this actually work? To grasp this we need to understand how memory works in a computer. Because there are only two states that can exist (on or off), every "bit" in memory can be thought of like a container that saves one of these two states. So to represent numbers larger than 1, we need to have bits that represent on/off for powers of two. For example, zero is 0, one is 1, but two is 10. If we wanted to represent four, it would be 100, eight would be 1000, and 16 would be 10000. This means that if two is 10, then three is 11, because 1 x 2 = 1, and 1 x 1 = 1, and 1 + 2 = 3. If we had the number eleven represented in binary, it would look like 1011, and we would say that the binary representation is "4 bits," or that it took 4 bits (separate containers for on/off states in memory) to represent the number eight. Study the graphic below:

![Alt binary_chart](http://www.sciencehq.com/wp-content/uploads/Binary-Decimal-Conversion.jpg)

There is more to binary that I am leaving out, because the rabbit hole gets much deeper, and one can find in universities a CS course devoted to nailing this down. [Wikipedia](https://en.wikipedia.org/wiki/Binary_code) has more on this topic, but an important concept which I won't get into here is the difference between ["signed" and "unsigned"](http://www.cs.cornell.edu/~tomf/notes/cps104/twoscomp.html) binary, aka ["two's complement"](https://www.youtube.com/watch?v=SXAr35BiqK8) (which solves the problem of [representing negative](https://en.wikipedia.org/wiki/Two's_complement) numbers in binary) 


<div style="text-align:center"><img src ="/../img/10-types.png" /></div>
<br>
Now to hexadecimal. Remember that numbers can be represented by any arbitrary symbols we want. So when we have really big numbers, or other complex pieces of information that we want to represent, how do we compress them into fewer bits? What is we could write fifteen with only one bit, instead of 4? We can. Hexadecimal is also known as base16, because we count from 0-9, but *then keep going* until we get to *F.* The chart below explains it so that I don't have to: 

![Alt hex](http://www.ee.nmt.edu/~rison/ee308_spr00/supp/000121/bin_hex_sign_unsign.gif)  
<br>

This allows us to faintly glimpse at a dim understanding of assembly languages, which use the hexadecimal numbering system in order to - get this - make them more "human readable." In earlier days, programmers worked directly with the memory of their machines, and they would manually issue commands for bits to jump from one slot to another in memory. These commands represent the logic of their calculations, and the results would be stored in memory. Hex makes it *slightly* easier for to humans to read and work directly with the processor and memory, but computers don't understand hex, so hex has to be [compiled into binary](https://www.youtube.com/watch?v=TFY8YuBLNKc) by an assembler. This makes assembler languages the first step off the ground in the [staircase of language levels](https://3.bp.blogspot.com/-btpK1XKZbWo/T9FBqYz3bjI/AAAAAAAABKA/qGt4MDRu0T8/s1600/level+of+programming+language.png). 

Importantly, [assembly languages](http://www.edwardbosworth.com/My3121Textbook_HTM/MyText3121_Ch01_V01.htm) are a set of processor instructions that generally have a one-to-one relationship with the architecture of the computer. They vary depending on the physical structure of the processor and its corresponding memory addresses. Again, [Wikipedia](https://en.wikipedia.org/wiki/Assembly_language#Assembly_language) says it better than I can, but what you should walk away with is at least a vague sense that the essence of programming relies on the scaffolding of abstractions that encode logic into the physical states of memory in the computer.

[This link](https://en.wikipedia.org/wiki/Assembly_language#Example_listing_of_assembly_language_source_code) explains the following code sample of an Intel assembler:

<div style="text-align:center"><img src ="/../img/assembler.png" /></div>
<br>

The activity of which looks roughly like this:

<div style="text-align:center"><img src ="http://math.hws.edu/eck/cs124/javanotes6/c1/overview_fig1.gif" /></div>
<br>

... And you see where this is going. I may be missing some history here, but I believe after assembly languages came [ALGOL](https://en.wikipedia.org/wiki/ALGOL), which is recognized as the ancestor of most modern programming languages, paving the way for FORTRAN (introduced by IBM in '57), BLISS, and C (developed by Dennis Ritchie from '69-'73 at AT&T). 

Understand the scaffolding: C needs to be compiled into binary in order to command the machine. It does this by relying on an assembler to calculate the correct way to convert C code into 10010111 11001010. On top of C, C++, or languages of the same level, are built a higher tier of programming languages, such as Python, Ruby, Scala... if you check under the hood of some Ruby core methods, you see C code:

{% highlight bash %}
♥ gem install pry
♥ gem install pry-doc
♥ pry
[1] pry(main)> show-source Array#sort

From: array.c (C Method):
Owner: Array
Visibility: public
Number of lines: 7

VALUE
rb_ary_sort(VALUE ary)
{
    ary = rb_ary_dup(ary);
    rb_ary_sort_bang(ary);
    return ary;
}
[2] pry(main)> 

{% endhighlight %}

And there you have it.

<!-- ![Alt wow](https://d262ilb51hltx0.cloudfront.net/max/600/1*cYl2zTitLZeKy29x2i0ApQ.jpeg) -->
<!-- ![Alt wow](https://gs1.wac.edgecastcdn.net/8019B6/data.tumblr.com/3249caebcdd1900dea346705d755421f/tumblr_mw4msoZcN81t0zii1o1_500.jpg) -->
![Alt wow](http://ih1.redbubble.net/image.15357201.6708/sticker,375x360.u1.png)


