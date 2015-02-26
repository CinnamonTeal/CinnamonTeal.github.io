---
layout: post
title:  "Types of Type"
date:   2015-02-23 07:07:56
---

Beginning programmers typically spend a lot of time trying to figure out what their first language should be - probably too much time. It makes sense, if you are about to start down a very long road, you at least want to be sure it's going to lead you in the direction you want to travel. Of course when you are a true beginner you don't know shit, and a lot of the various pros and cons for each language were way over my head. Now that I have been eating, drinking, breathing, shitting, and dreaming about Ruby 24/7 for the past 5 weeks at the Flatiron school, I am at least clueful enough to appreciate some of the finer differences between languages. But I remember reading about various programming languages, and coming across terms such as  "strongly typed" or "weakly typed." Also confusing is the difference between "static typing" and "dynamic typing." So, okay... wtf does that mean? 

Go ahead and laugh, but at one time I actually wondered if it had something to do with actually typing, on a keyboard. Like... did "strong typing" mean pressing the keys harder or something? (Why the fuck would they name it that?)

Yeah... no. When describing programming languages, "typing" actually means determining the data type for variables. Typing as in categorizing. As in setting the type. 

There seems to be a lot of confusion and debate on forums about the differences between these 4 terms, so let me dispel the confusion right off the bat. Strong and weak typing are mutually exclusive - they are opposite poles of the same axis. The same is true about static and dynamic typing. But it is possible to have a strongly AND dynamically typed language (such as Ruby). So there are really two axes, strong vs weak, and static vs dynamic.

Here's the breakdown:

  - Strong Typing:

    Strong typing means that variables are restricted to a specific data type. You can't mix up things like, say, a string and a fixnum, or a fixnum and a float. They are different data types, and their data types are fixed. Ruby is strongly typed, therefore you can do things like:


{% highlight Ruby %}
  a = "99"
  b = " Luftballons"
  a + b
    =>  "99 Luftballons"
{% endhighlight %}

    but Ruby will shit the bed if you try this: 

{% highlight Ruby %}
  a = 99
  b = " Luftballons"
  a + b
    => "TypeError: String can't be coerced into Fixnum"
{% endhighlight %}
  
  Notice the quotes around "99" in the first example. Because that 99 is a string (not a Fixnum), it will play nicely with other strings. But the 99 in the second example is not a string, it's a Fixnum, which lets you do math and other numbery things with it, but not scrambling, concatenating, sorting or other wordy, 'stringy' things with it. 

  - Weak Typing:

  Javascript on the other hand is weakly typed. Like honey badger, it doesn't care what you do with your variables. It will mix strings and integers and whatever types you throw at it, but the outcome is often unpredictable. In the hands of someone who knows what they are doing, this can be used skillfully, but for most programmers, the freedom to mix data types willy nilly ends up becomming rope with which to hang onself and the source of many bugs.

  It is for these reasons that the difference between strong and weak typing is also referred to as "type safety," with strong type being the safer type.

  - Static Typing:

  In a statically typed programming language (such as Java, C and C++), variables do not need to be defined before they are used, but they do need to be initialized (or declared). Checkout this C++ code:

  {% highlight c++ %}
    int counter

    counter = 1
    while (counter <= 10)
      {
      cout << "do something"
      counter ++
      }
  {% endhighlight %}

  In this example, the variable "counter" is declared (or initialized) without a value, but with a data type (int). Once counter is an int, it will forever be an int. That is static typing. 

  - Dynamic Typing

  In a dynamically typed language however (such as Ruby or Python), you can initiate variables and set their values at the same time, on the fly. Later if you change your mind, or you want to recycle that variable so you can perform different types of operations on it, changing the variable type is supported. Ruby has a set of built in methods that make this easy. Observe:

  {% highlight ruby %}
x = 10
x.to_s
  => "10"

sentence = "this is a string"
sentence.split(' ')
  => ["this", "is", "a", "string"] 
  # actually now it's an array of strings

  {% endhighlight %}

  Voila. Dynamic typing is convenient because you don't have to initialize variables, and data manipulation becomes far easier. If you want this object to behave like a string, but you need to iterate over it like an array, then you can (as per the example above) call a method to split your string into an array of strings, etcetera. 


  Now you know. 


