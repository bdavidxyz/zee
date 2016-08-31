



<h1 align="center">Zee</h1>
<div align="center">Dead simple, conversion-focused landing page builder.</div>

## [Read intro, features & benefits here &rarr;](http://bdavidxyz.github.io/zee)


<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  

- [Intro](#intro)
- [Quickstart](#quickstart)
  - [Prerequisite](#prerequisite)
  - [Develop](#develop)
    - [1. Scaffold and start a server](#1-scaffold-and-start-a-server)
    - [2. Add, edit, remove as many section as you need](#2-add-edit-remove-as-many-section-as-you-need)
    - [3. Change atmosphere quickly](#3-change-atmosphere-quickly)
    - [4. Deploy to GitHub pages](#4-deploy-to-github-pages)
- [Directory structure](#directory-structure)
- [Add 3rd party lib](#add-3rd-party-lib)
  - [Add a Javascript lib](#add-a-javascript-lib)
  - [Add a CSS lib](#add-a-css-lib)
  - [Add a SASS lib](#add-a-sass-lib)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->





## Intro

Zee allows you to create a clean, minimalistic but well-targeted, high-converting landing page.

The landing page you will get is based on Bootstrap 4, jQuery 2, Google Analytics. 

You can of course add any 3rd party-lib, and customize the page as much as you want.

Deployment will occur on GitHub pages by default.





## Quickstart

### Prerequisite


 - [Ruby](https://www.ruby-lang.org/en/downloads/) - use the installer
 - [Jekyll](https://jekyllrb.com/) - ```$ gem install jekyll```
 - [NodeJS](https://nodejs.org/en/download/) - use the installer.

Tested with : node 5.12.0, jekyll 3.1.6, ruby 2.3.0


### Develop


#### 1. Scaffold and start a server

```shell

$ git clone https://github.com/bdavidxyz/zee
$ cd zee
$ npm install
$ npm run generate # will scaffold the entire directory structure
$ npm run local # opens a browser that will auto-refresh on every change
```

#### 2. Add, edit, remove as many section as you need

Open another tab in your CLI

```shell

$ npm run add-section # will ask you which section you want to add
$ npm run rm-section # will ask you which section you want to remove
```

#### 3. Change atmosphere quickly

```shell

$ npm run update-theme # will ask you which heading font, display font and primary color you want
```

For the fonts, use the google format, as the example below

<code><span style="color:grey">Which font do you want as heading ? (type name of a google web font)</span> Roboto+Condensed:700</code>

<code>Which font do you want as display ? (type name of a google web font) Roboto:300,400,700</code>

<code>Which color do you want as primary color ? (for ex. #0275d8) blue</code>

The tool was primarily designed with these two font above, so try to stick to the font weight to have a better user experience.



#### 4. Deploy to GitHub pages

- 1) **Stop the local server (Ctrl + c) in the command-line**
- 2) Empty the local git configuration <code>$ rm -rf .git</code>



- 3) **create a GitHub repository** and **hook it to your project** by following this tutorial : https://help.github.com/articles/adding-an-existing-project-to-github-using-the-command-line/
- 4) run this command <code>$ npm run deploy</code>




## Directory structure

Here are the interesting parts

```shell
-index.html        # Sections are included here.
-_includes/
  |__html/
    |__zee/        # Here are HTML of sections you may want to modify 
  |__javascript/
    |__bootstrap/  # 3rd party JS lib like bootstrap.js
    |__zee/        # JS of sections
-_sass/
  |__zee/          # CSS of sections
  |__bootstrap/    # 3rd party CSS lib like bootstrap.scss
```





## Add 3rd party lib

As of now, the inclusion of a 3rd party lib is manual.

I'm working on a more declarative way to solve this.


### Add a   Javascript lib

Example with flipclock.js

a. create a new file _includes/javascript/flipclock/flipclock.js.html

b. insert in the file the code below

```javascript
<script type="text/javascript">
</script>
```

c. copy/paste the code of flipclock.js inside the "script" tag

d. optionnally remove the exclamation mark when you encounter comments like /*! 

e. include the lib in the build pipeline inside <code>_layouts/default.html</code>

```html
{% include javascript/flipclock/flipclock.js.html %} 
```

### Add a CSS lib

Example with flipclock.css

a. copy flipclock.css into _sass/flipclock/flipclock.css

b. optionnally remove the exclamation mark when you encounter comments like /*! 

c. optionnally remove all vendor prefixes of the css lib.

d. in file css/main.scss, above comment <code>// end-extlib </code>, add the code below

```sass
@import "flipclock/flipclock.css";
```


### Add a SASS lib

Example with bourbon.scss

a. copy all file & folders of bourbon _sass/bourbon

b. optionnally remove the exclamation mark when you encounter comments like /*! 

c. optionnally remove all vendor prefixes of the css lib.

d. in file css/main.scss, above comment <code>// end-extlib </code>, add the code below

```sass
@import "bourbon/bourbon.scss"; // the main entry point of the SASS lib
```
 
