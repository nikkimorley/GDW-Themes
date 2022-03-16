# GDW-Themes
Collaborative Build Repo for GDW Themes

## Structure of this Repo
There will be a template folder with all the base files needed to build a theme. This template folder will be cloned for each theme with assets and notes added to it. 

## Steps to Get An Environment Running
You will want to use VS Code as your code editor in order to use the Live Server extension as well as the Easy LESS extension. 
### Less
We're going to make our lives easy and use the Easy LESS VS Code Extension by mrcrowl. Make sure you have this installed. All you will need to do now is save a less file and it will compile to CSS. Easy peasy.

### Spin Up A Server
Make sure you have the Live Server extension installed by Ritwick Dey.

Once installed and enabled, while on the index.html page, go to the lower right of your VS Code window and click the "Go Live" text to spin up a server. A new localhost will appear in your browser.

Alternatively, you can also right click on the index.html file and select "Open with Live Server".

## Coding a Theme

You will want to read through the template.less (or template.css) file. There are a lot of helpful hints here on common practices when building themes for GDW, links to the libraries we use, and documentation for classes built into our platform that you are welcome to use in the theme.

GDW is using a desktop first approach and using media queries to scale down. There is an example class called `.example-class` in styles.less as well as an example element in index.html that will illustrate this concept and how to include media queries within the class.

There are also media queries in the bottom of styles.less reflecting our old method of media queries in themes. The preferred method of writing media queries within the class is preferred.


### Lighten, Darken, Tint, Shade 

TBD


### Retina and Images

TBD

### Pull Requests

TBD

### visible-xs, hidden-xs

TBD


### @desktop vs @screen-lg

TBD