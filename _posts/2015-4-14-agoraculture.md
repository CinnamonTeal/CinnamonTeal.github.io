---
layout: post
title: 1 Week Project - Agoraculture
---

![Alt Agoraculture](/../img/agoraculture.png)

**4.14.15** 23:17

Last week I built my first full-scale Rails app with the help of my friend and Flatiron classmate Shawn Hansen. It's called Agoraculture, and it helps users find the nearest and/or best farmers' markets in their area (although currently limited to NYC).

In ancient Greece, the agora was the city center where people congregated to participate in the social, artistic, athletic, political, philosophical et al. happenings of the time. Today, farmers' markets are the modern day agora, therefore I thought the name Agoraculture was a pretty clever pun (when pronounced correctly, like "AAAG-ora", not "a-GOra"). 

It was a nice transition to go from doing lab exercies to actually building something. Here are some of the challenges we faced and overcame:

1. Javascript is "asynchronous." A central concept to this which I think I finally (mostly) grasp, is the idea of promises. Javascript makes use of event listeners, so that when it is loaded, it can sit on the client waiting for actions which might change the state of a script, and any number of other scripts depending on it. This can create a bit of a confusing maze of dependencies I imagine, but having not learned much javascript yet we were a bit lost until we realized what was happening. TL;DR: When using the GoogleMaps API for our market locator, our app was trying to load pins before it loaded the map, until we learned how to make it work. 

{% highlight javascript %}
var geocoder;
var map;

function initialize() {
  geocoder = new google.maps.Geocoder();
  var latlng = new google.maps.LatLng(40.697325, -73.986014);
  var mapOptions = {
    zoom: 12,
    center: latlng
  }
  // this seems obvious now, but the map has to be loaded first
  map = new google.maps.Map(document.getElementById('map-canvas'), mapOptions);
}

// otherwise there is no map to put the location pins on
function addPin(market) {
  var lat = market[1];
  var lon = market[2];
  var marketLatlng = new google.maps.LatLng(market[1], market[2]);

  var marker = new google.maps.Marker({
    map: map,
    position: marketLatlng,
    // url: "market/" +  market[0]
  });

  google.maps.event.addListener(marker, "click", function(){
    window.open("market/" + market[0]);
  });
}
{% endhighlight %}

2. (markdown is stupid with numbered lists - ignore this line) 

2. Bootstrap is supposed to be easy, but pay attention to the theme that you choose. We chose a theme from wrapbootstrap.com, called "Vitality." At first it looked like a sleek and beautiful theme, but it was a nightmare to try and integrate. After consulting with our instructors, the consensus seems to be that our theme was just poorly written, breaking many best practices, and thereby causing us confusion. At the time of this writing we are shopping for a new theme, this time carefully using the chrome devtools to inspect the javascripts and css on the pages of the themes' demos, to ensure we know what we are getting into. 

3. Pair programming is a productivity **turbo**. Your mileage may vary, but we found that when working on a new feature which required new and unfamiliar skills/tools, we covered twice as much ground in half the amount of time whenever we put all of our brain on the same problem. We'd start by pushing and pulling from github to ensure we were on the same page, then, while googling and stackoverflowing together we could try out our different ideas in the console simultaneously until one of us won the race to the solution. Also, working on the same feature together kept us focused, whereas dividing up the work and working separately was really more like working alone. 

4. Video backgrounds on home pages look fuuuuuucccckiiiinngg awesome. I actually went to the farmers market and shot several short video clips, so that we could dynamically change the background video on our home page everytime the page loads, using a simple hack I came up with in ruby which interpolates the filename:

{% highlight javascript %}
// Video Background Settings
   $("header.video").wallpaper({
       source: {
           poster: "assets/img/bg-mobile-fallback-arugula.jpg",
           // here is the magic incantation:
           mp4: "assets/mp4/#{rand(1..4)}.mp4"
       }
   });
{% endhighlight %}

Another, more "javascripty" way to do this (which we later learned) is to simply use "+ randomNumber +"

{% highlight javascript %}
// Video Background Settings
   $("header.video").wallpaper({
       source: {
           poster: "assets/img/bg-mobile-fallback-arugula.jpg",
           // here is the magic incantation:
           mp4: "assets/mp4/" + randomNumber + ".mp4"
       }
   });
{% endhighlight %}

It was really satisfying to attempt something totally unprepared, sail through stormy seas, and somehow come out alive (albeit totally sleep deprived) at the end. I can't wait to buld our next Rails app, which will be a 3 week project. 