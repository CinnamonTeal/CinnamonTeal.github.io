---
layout: post
title: Struct Your Stuff
---

**3.9.15** 22:29

<!-- - blog - about Structs in ruby (what they are, how they work, how to use them, why they're awesome) -->

I recently learned about a handy Ruby class called [Struct](http://ruby-doc.org/core-2.2.0/Struct.html).

Normally when creating a class, it needs to be initialized with a minimal group of methods known as 'setters' and 'getters,' (aka 'readers' and 'writers') which allow you to give and get information about that class. The setup looks like this:

{% highlight Ruby %}
class Person

# this sets the name
def name=(n)
  @name = n
end

# this gets the name 
def name
  @name
end
{% endhighlight %}

Even better, use attribute accessors:

{% highlight Ruby %}
class Person

attr_reader :name # implicitly creates the getter method
attr_writer :name # implicitly creates the setter

# implicitly creates both set/get methods simultaneously, 
# although not always preferred.
attr_accessor :name 
{% endhighlight %}

All of this so far is pretty basic and straightforward. But sometimes you don't actually need a named class, you just want a quick and dirty object that behaves like a class.

{% highlight Ruby %}
Person = Struct.new :name, :address  
{% endhighlight %}

Whatever arguments you pass to Struct.new will be the names of attributes that you basically hardcode into the Struct, therefore they must be symbols, just like you would use with an attr_accessor. In addition to having attribute accessors, Structs also come with other hidden capabilities. For example you can actually inherit from a Struct just like you would from a regular class, but you can make it up on the fly:

{% highlight Ruby %}
class Person < Struct.new(:height, :weight)
end

Bob = Person.new(6, 180)
{% endhighlight %}

Or you could also do:

{% highlight Ruby %}
Person = Struct.new(:height, :weight)
Bob = Person.new(6, 180)

[1] pry(main)> Bob.height
=> 6 
{% endhighlight %}

You can even define your own methods by passing Struct a block:

{% highlight Ruby %}
[1] pry(main)> Bob = Struct.new :height, :weight do
[1] pry(main)*   def body_mass_index
[1] pry(main)*     return @height / @weight
[1] pry(main)*   end  
[1] pry(main)* end  
=> Bob
[2] pry(main)> 
{% endhighlight %}

Oddly, when you create a Struct, it isn't actually an instance of the Struct class, but rather an instance of the Class class which descends from the Struct class...

{% highlight Ruby %}
[1] pry(main)> Person = Struct.new :name, :address
=> Person
[2] pry(main)> Person.class
=> Class
[3] pry(main)> Person.ancestors
=> [Person, Struct, Enumerable, Object, PP::ObjectMixin, Kernel, BasicObject]
{% endhighlight %}

So basically Struct is a nice shortcut for single serving class functionality, that you can use to save time and type less. I am looking forward to experimenting more with Structs to see what else I can use them for!
