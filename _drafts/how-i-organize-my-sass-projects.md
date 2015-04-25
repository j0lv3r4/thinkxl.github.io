---
layout: post
title: How I organize my Sass projects
tag: Sass 
author: Juan Olvera
twitter: thinkxl
---

This is a basic writing on how I organize my Sass projects, mostly for self documentation than trying to tell "this is the right way to do it".

I use two kinds of structures, Mid &amp; small-size projects. I focus mostly on small business and that's why this doesn't require too much complexity.

## Small projects

{% highlight bash %}
vendors/ # Use this if they are not inserted using bower install
  |-- _normalize.scss
  |-- _colorpicker.scss
utils/
  |-- _functions.scss # All mixins, functions, extends, etc.
base/
  |-- _base.scss # Base, typography, etc.
components/ # Micro components
  |-- _buttons.scss
  |-- _navigation.scss
  |-- _dropdown.scss
  |-- _comments.scss
  |-- _listings.scss
layout/ # Macro components
  |-- _layout.scss # Header, container, footer
  |-- _sidebar.scss
  |-- _grid.scss
pages/ # Specific pages styles
  |-- _pages.scss # Home, contact
todo.scss # Styles that I can organize later
main.scss # The manifest
{% endhighlight %}
 
## Mid-size projects

{% highlight bash %}
vendors/ # Use this if they are not inserted using bower install
  |-- _normalize.scss
  |-- _colorpicker.scss
utils/
  |-- _variables.scss
  |-- _functions.scss
  |-- _mixins.scss
  |-- _extends.scss
base/
  |-- _base.scss
  |-- _typography.scss
components/ # Micro components
  |-- _buttons.scss
  |-- _navigation.scss
  |-- _dropdown.scss
  |-- _comments.scss
  |-- _listings.scss
layout/ # Macro components
  |-- _header.scss
  |-- _container.scss
  |-- _footer.scss
  |-- _sidebar.scss
  |-- _grid.scss
pages/ # Specific pages styles
  |-- _home.scss
  |-- _contact.scss
todo.scss # Styles that I can organize later
main.scss # The manifest
{% endhighlight %}

In both sizes I use the same folders and each one have their own purpose on what they serve.

### `vendors/`

When I don't use [Bower](http://bower.co) for third party libraries, this is the folder where they go.

### `utils/`

Here are the files that include functions, mixins, extends, or classes that I use more than once in different folders.

Notice that if I use a mixin only once, I include it inside the file where is needed, for example I have a `button-generator` mixin that I only use on `_bottons.scss` so I have it included in there only.

### `base/`

Core styles for `html`, `body`, `p` and `a` tags. In other words, the foundation (not the framework) of the project.

### `components/`

Here are all the UI components that are required to use in different areas.

### `layout/`

Header, footer, sidebar and other elements that makes the site structure. I build layouts with the help of the components, for example, the header is built with the `.site-logo`, `.site-navigation`, `.social-icons`, and the necessary <abbr>CSS</abbr> to put everything in their place. 

### `pages/`

Page specific styles, for example: 

- `_home-page.scss` 
- `_contact-page.scss`
- `_portfolio-gallery.scss'`

### `main.scss`

The manifesto that include all the files to render the `style.css`.

**Why `normalize.css` is in vendor? everybody put it in `base/`**

Well, `normalize` is a third party library in the most literal sense, and that's why, I think it should be in there.
