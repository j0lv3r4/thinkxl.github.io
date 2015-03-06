How I organize my Sass projects
-------------------------------

This is a basic writing on how I organize my Sass projects, mostly for self documentation than trying to tell "this is the right way to do it".

I use two kinds of structures, Mid &amp; small-size projects. I focus mostly on small business and that's why this doesn't require too much complexity.
 
## Mid-size projects

```
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
```

## Small projects

```
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
```

In both sizes I use the same folders and each one have their own mission on what they serve.

### Vendors

I use [Bower](http://bower.co) as my package manager for third party libraries, but for some reason I download some files manually, and then this is the folder where they go.

### Utils

Here are the files that include functions, mixins, extends or classes that are intended to use more than once in different folders.

Notice that if I use a mixin only once, I include it inside the file where is needed, for example I have a `button-generator` mixin that I only use on `_bottons.scss` so I have included it in there.

### Base

Core styles for `html`, `body`, `p` and `a` tags, basically the foundation (not the framework) of the project.

### Components

Here are all the UI components that are required to use in different areas

### Layout

This are the files I use for sections, elements and other stuff that help build the structure of the site. Here is where I use the `components` to help me build the architecture of the site.

### Pages

If a page has a specific style that is going to be only used in there, I create a file with the name of the page and include the styles in there.

### `main.scss`

The manifesto that include all the files to render the `style.css` minified and all those magic steps.

## Things that I should do

- Include a manifest per folder, I have seen [Dale Sande](https://vimeo.com/86306772) use it this way.

## FAQs

**Why `normalize.css` is in vendor? everybody have it in `base/`**

Well, the true is that `normalize` is a third party library, in the most literal sense and that's why I think it should be in there
