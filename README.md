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


### Color Functions

GDW uses five main color functions from LESS to modify colors. It's ideal to use these functions if you are trying to create a version of a color so that the code updates gracefully if the original color (defined in a variable) is being updated.

For example, if you have a color variable of @themeColor1 and you want to lighten it a little on hover, it makes most sense to define in the hover definition `color: tint(@themeColor1, 10%)`. This color function will add 10% white to @themeColor1 and thus making it appear lighter. 

#### Four color functions and what they do:
tint(color, percentage) - Mix color with white in variable proportion.
shade(color, percentage) - Mix color with black in variable proportion.
lighten(color, percentage) - Increase the lightness of a color in the HSL color space by an absolute amount.
darken(color, percentage) - Decrease the lightness of a color in the HSL color space by an absolute amount.
fade(color, percentage) - Set the absolute opacity of a color. Can be applied to colors whether they already have an opacity value or not.

You can find more color functions in the LESS documents here: https://lesscss.org/functions/#color-operations

### Retina and Images

Certain computers have a Retina display which are designed to show a sharper image. A Retina image is an image created specifically to look sharp on a Retina display. SVGs, since they are vector images, naturally look sharp on a Retina dislay. 

For raster images like .jpgs and .pngs, they will need to be created at twice the size becuase we will need to double the amount of pixels in the display. The XD file will naturally have the retina display images ready for you when you download the image. The retina image will have @2x at the end of the name, before the extension.

Note: If you change the name of an image, be sure to change it on both files but leave the @2x.
### SVGs that need to be modify by user interaction

Generally if you are linking an svg that is just acting like an image, you can simply link it via the <img> element.

However, if you need to modify your svg via a user interaction (like a hover), you will need to include your svg code in the HTML itself which will give you control over the code.

To do this, open the svg in VS Code and copy the code and paste the code where it will exist in the DOM (usually within a parent element to contain it).

### Responsive Sizing Cheat Sheet

You will see two sets of media query definitions. The largely differ in their site build approach. GDW uses a desktop first approach so global css styles (styles created that don't exist within a media query) will target all sizes and media queries start at 1200px and go down. (Anthing at 1200px and smaller, then anything at 992px or smaller, then anything at 768px or smaller, then anything at 380px or smaller.)

Bootstsrap on the other hand, uses a mobile first approach, so global styles will target all sizes but media queries will break the size into four breakpoints and start with the mobile (anything less than 768px, then anything greater than 768px, then anything greater than 992px, finally anything greater than 1200px).

A visual representation of the info above:

#### GDW - Desktop first Approach     
|@mobile-xs   |@mobile   |@tablet   |@desktop    |No size definition              |
|-------------|:--------:|:--------:|:----------:|:------------------------------:|
|≤480px       |≤768px    |≤992px    |≤1200px     |>1200px & undefined breakpoints |

#### Bootstrap - Mobile first approach                                            
*-xs         |*-sm      |*-md     |*-lg         |No size definition               |
|------------|:--------:|:--------:|:----------:|:-------------------------------:|
<768px       |≥768px    |≥992px   |≥1200px      |Global                           |

This is a little hard to wrap your head around so here is a handy cheat sheet. You'll mentally be in the GDW media query headspace, so when you need to find the corresponding bootstrap css class, this table may be helpful. 

GDW        | Bootstrap |
|----------|:---------:|
Global     | *-lg.     |
@desktop   | *-md      |
@tablet    | *-sm      |
@mobile    | *-xs      |
@mobile-xs | Global    |

### Bootstrap Responsive Utility Classes

Bootstrap has some very handy classes to use that response to Bootstrap's defined container sizes. You can find the documentation for it here: https://getbootstrap.com/docs/3.3/css/#responsive-utilities

In a nutshell, use hidden-* or visible-* to hide or show elements at various breakpoints. These breakpoints are very literally designed however and you can't cascade them. So if you want an element to be hidden in the xs and sm breakpoints, it will need either `hidden-xs hidden-sm` or `visible-md visible-lg` in its class attribute.

### Pull Requests

TBD - I will make a process for this.

