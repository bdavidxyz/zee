



<h1 align="center">Zee</h1>
<div align="center">Dead simple, conversion-focused landing page builder.</div>

## [Read intro, features & benefits here &rarr;](http://bdavidxyz.github.io/zee)


<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  

- [Zee](#zee)
  - [Quickstart](#quickstart)
    - [Prerequisite](#prerequisite)
    - [Develop](#develop)
    - [Deploy](#deploy)
  - [Sections](#sections)
    - [What it is](#what-it-is)
    - [How to include a section](#how-to-include-a-section)
  - [Customization](#customization)
    - [Change theme](#change-theme)
    - [Build your own theme](#build-your-own-theme)
    - [Cutomize a section](#cutomize-a-section)
  - [Warnings](#warnings)
    - [Bootstrap 4 officially not yet ready](#bootstrap-4-officially-not-yet-ready)
    - [Bootstrap Javascript is disabled](#bootstrap-javascript-is-disabled)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->




## Quickstart

### Prerequisite


 - [Ruby](https://www.ruby-lang.org/en/downloads/) - use the installer
 - [Jekyll](https://jekyllrb.com/) - ```$ gem install jekyll```
 - [NodeJS](https://nodejs.org/en/download/) - use the installer.
 - [GulpJS](http://gulpjs.com/GulpJS) - ```$ npm install -g gulp ```

Tested with : node 5.11.1, npm 3.8.6, gulp 3.9.1, jekyll 3.1.6, ruby 2.3.0

### Develop


```shell

$ git clone https://github.com/bdavidxyz/zee
$ cd zee
$ npm install
$ gulp
 # The browser launches itself,
 # and will rebuild and live-reload each time you
 # change a file
```

Change text inside _includes/ownhtml/own-hero0.html.

The change should reflect in the browser immediately.

### Deploy

The tool comes with a prebuilt command to deploy to github pages : it's free.

```shell

$ gulp deploy
 # You can view and share your website at https://github.com/<your_github_name>/<your_github_repo>
```


## Sections

You build a unique one-page website by adding and editing sections.

### What it is

A section is a part of a landing page : pricing table, testimonial, our team, etc.

Each section has many designs, so that can choose the one you prefer. For example :

 - Designs of pricing tables : pricingtable1, pricingtable2, etc
 - Designs of testimonials   : testimonial1, testimonial2, etc
 - Designs of navigation bars   : navbar1, navbar2, etc

For a given design, there are 3 file, for example : 
 - _includes/html/zee/navbar1.html (HTML is mantory)
 - _sass/zee/navbar1.scss (CSS file may or may not be required)
 - _includes/javascript/zee/navbar1.js.html (JS file, may or may not be required)

**⚠️ You must include all needed files (min 1 - max 3) for a given section (see below)⚠️**


### How to include a section

Example with navbar1.

Inclusion of html : in file **index.html**

```html
  <!--include HTML section here, 
  don't forget to include SCSS and JS 
  for a given section, if apply-->
  {% include html/zee/navbar1.html %}
```

Inclusion of css (if apply) : in file **css/main.scss**

```css
//Import SCSS of sections here
@import "zee/navbar1";
```

Inclusion of js  (if apply) : in file **_layout/default.html**

```js
    <!--startjs-->
      {% include javascript/zee/navbar1.js.html %}
    <!--endjs-->
```
(put the line right above the endjs comment to allow 3rd party lib to load first
)



## Customization

### Change theme

You can change theme by editing _data/theme.yml.
Choose amongst the availables pre-defined themes.

You are encouraged to create your own theme, it's very easy and may suit your needs better.


### Build your own theme

There are very few changes to make in order to get a new theme.

Open css/main.scss, and look for line

```
//CREATE YOUR OWN THEME BELOW
```

And modify listed parameters under this comment.
There are not so many parameters to change, 

### Cutomize a section

Each section is basically a bootstrap 4 snippet. 
There are very few changes compared to plain old bootstrap.
Even the theme variables are actually bootstrap-based SASS variables.

If you already met this framework, even in lower version, customize and create a section should be very easy.


## Warnings

### Bootstrap 4 officially not yet ready

But used here, the use of flexbox is very convenient in many scenarii, amongst other goodies.

### Bootstrap Javascript is disabled

High performance is a high priority for the tool, therefore Javascript modules are disable. Simply uncomment them in _layouts/default.html to use them.

