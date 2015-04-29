---
layout: post
title: Model View Controller
---

**4.27.15** time?


When I first learned about MVC, I had only ever heard of it in the context of a Rails app, so I thought it was unique to Rails. What I've learned now is that actually MVC is a design pattern (which Rails actually deviates from in some ways), that is followed by several other web development frameworks, and is essentially one way of attempting to solve the problem of 'separation of concerns.'

So what is it? If you've never heard of it, Model View Controller means that there are (at least) 3 separate components to your app. I am most familiar with Rails so we will start with Rails as the example. One idea in Rails is to try and use object orientation design principles for the web, so Rails comes with a feature known as ActiveRecord, which makes it easy to access your sql database without having to write sequel - it allows tables in your database to correspond to ruby objects. In the context of the MVC design pattern, the objects in your ruby code correspond to "models" in your database. 

For example, let's say you're building an e-commerce site. Well, you're gonna have Users, and those Users are going to be both Sellers and Buyers. Sellers are going to have Items to sell, and Buyers are going to (hopefully) buy those Items. So in your database, you might "model" the data as Users and Items, and since Buyers and Sellers are really just Users, they would exist as "foreign keys" for the User model (more on that later). ActiveRecord is handy because it let's us use syntactically friendly and familiar ruby methods to access the database, by writing sequl for us. So when we want to find out how many Users we have, we might call the .all method:

{% gimme some sample code %}
User.all
  > all mah users biatch

but the SEQUEL looks like (SELET * from Users where *  is whatever)