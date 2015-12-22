---
layout: post
title: Second Model inside a View using Backbone 
tag: JavaScript 
author: Juan Olvera
twitter: thinkxl
---

Trying to build a mobile app for a client I needed to add a second model inside a single view, apparently it doesn&rsquo;t work out of the box. 

After googling for a while, without success, I decided to go to the IRC and ask in there. As I expected I got the answer right away.

When you try to initialize a view inside a route like this:

{% highlight javascript %}
// routes.js
var Router = Backbone.Router.extend({
  routes: {
    'app': 'home'
  },

  initialize: function() {
    console.log("Route initialized");
  },

  home: function() {
    new HomeView({ 
      model: userModel, 
      client: clientModel 
    });
  }
});

var route = new Router();
{% endhighlight %}

And try to access it like this:

{% highlight javascript %}
// views.js
var HomeView = Backbone.View.extend({
  el: '.app',

  template: App.Templates.home,

  events: {},

  initialize: function() {
    this.render();
    console.log(this.client); // Trying to access `clientModel`
  },

  render: function() {
    this.$el.html(this.template);
  }
});
{% endhighlight %}

It won&rsquo;t work. 

## Solution

You will need to get the second model from the parameters passed in the `initialize` function when you create the view:

{% highlight javascript %}
var HomeView = Backbone.View.extend({
  el: '.app',

  template: App.Templates.home,

  events: {},

  // `params` argument let us access the parameters 
  // passed on this function
  initialize: function(params) { 
    this.render();
    this.client = params.clientModel;
    console.log(this.client); // now we can access it
  },

  render: function() {
    this.$el.html(this.template);
  }
});
{% endhighlight %}

Thanks to **systemfault** on `##frontend` for help me figure it out.
