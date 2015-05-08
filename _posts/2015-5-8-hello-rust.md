---
layout: post
title: Hello Rust!
---

**5.8.15** 9:23

Rust is a general purpose, multi-paradigm, compiled programming language developed by Mozilla Research. My understanding is that it's *like* C++, only faster (or at least similarly fast) and "safer." Anyway it has a cool name, and I want to learn something a little closer to the metal than javascript and ruby, so here's how to get started with your first Hello World program:

First thing, you need to install Rust. Head over to the [rust website](http://www.rust-lang.org/) for instructions on getting it installed.

Once you have Rust, make a directory for your Rust projects, cd into it, and create a file called hello_world.rs. 

Type this out, save the file: 

{% highlight Rust %}
fn main() {
  println!("Hello, world!");
}
{% endhighlight %}

and then run it in terminal:


{% highlight Rust %}
$ rustc main.rs
=> Hello, world!
{% endhighlight %}

It works! Let’s go over what just happened:

{% highlight Rust %}
fn main() {

}
{% endhighlight %}

These lines define a function in Rust. Every Rust program begins with a main function like this. The first line says "I’m declaring a function named main which takes no arguments and returns nothing." If there were arguments, they would go inside the parentheses (( and )), and because we aren’t returning anything from this function, we can omit the return type entirely.

Also notice that the function is wrapped in curly braces ({ and }). Rust requires these around all function bodies. It is also considered good style to put the opening curly brace on the same line as the function declaration, with one space in between.

