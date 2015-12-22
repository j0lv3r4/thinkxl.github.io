---
layout: post
title: Introducing Rocketbin
tag: Projects 
author: Juan Olvera
twitter: thinkxl
intro: Today I&rsquo;m excited to launch my first Flask app named Rocketbin.
---

There is a stage in the life of a front-end developer where we want to build our own back-end. 

We want to be able to manipulate databases, build APIs, and all that cool stuff that we need to make cool apps.

### The micro-framework

Recently I started to play with [Flask](http://flask.pocoo.org/), a micro-framework for Python based on [Werkzeug](http://werkzeug.pocoo.org/), [Jinja2](http://jinja.pocoo.org/docs/dev/) (A templating language) and good intentions. 

Because its simplicity, the amount of documentation and the community involved in the project, I found Flask a very good fit in my needs.

### First Project

For my first project I wanted to create a [Pastebin](http://pastebin.com) clone, using *Python* in the back-end and *JavaScript* in the front-end.

### Why Not Node?

I found Python a lot simpler than Node, that&rsquo;s it.

### So... What is Rocketbin?

[Rocketbin](http://rocketb.in) is a very simple Pastebin clone, without user management, without title and with a very few supported languages:

- HTML
- CSS
- Sass
- Less
- JavaScript
- CoffeeScript
- Python
- Ruby
- PHP

### Features?

Most of the features are provided by [Ace](http://ace.c9.io/) in the editor, and those include:

- Syntax highlighting using Github theme
- Automatic indent
- Live syntax checker
- Emmet
- Vim and Emacs key bindings
- Autocompletion

Here are some gifs to show the features in action:

*Autocomplete in JavaScript*

![image]({{ site.url }}/public/img/autocomplete-js.mov.gif)

*Autocomplete in Python*

![image]({{ site.url }}/public/img/autocomplete-python.mov.gif)

### What technologies are involved?

**Back-end**

- Flask
- MongoDB

**Front-end**

- <abbr>HTML</abbr>
- <abbr>CSS</abbr> using Sass
- jQuery (Yes I&rsquo;m lazy)

Obviously this is an [open-source project](https://github.com/thinkxl/rocketbin), hosted in [Github](http://github.com) with a [GPL License](https://github.com/thinkxl/rocketbin/blob/master/LICENSE).

This is still a work in progress, so if you find any bug please submit a ticket on the [Github repository](https://github.com/thinkxl/rocketbin/issues).

Happy Coding!
