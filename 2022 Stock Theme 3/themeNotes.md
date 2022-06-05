2022 Stock Theme 3

XD File: https://xd.adobe.com/view/c1c11976-f2fc-4805-a340-a21565a9a1d5-9492/

Notes:
Some of this text is incorrect and will need to be updated on my end. Also, some things like the background for the h1 text in #main isn't perfectly even, but make that padding even left and right. It's even everywhere else. :) 

Let me know if you have any questions!


Notes regarding text in the banner area: 

I think I know where your head is at. If I am to guess, you're trying to include the image via <img> tag so that it scales well in mobile. This is good! However, in the desktop views it's also a bit of a problem which is what you're encountering. 

Absolutely positioning the text will be a problem because since this is a stock theme, the client can put whatever they want in the text. When the text gets too big, if it's absolutely positioned, it will break the container if it gets too big. 

The solution for this is to use a css background image in the desktop and maybe the tablet sizes depending on how things are looking, and then when you want the text to stand alone either above or below the image, we switch to the <img> tag. The way we do this, is when we are ready to do the switch, you will target the media query and remove the background in the css file. Simultaneously we will utilize some built in bootstrap classes on the <img> tag.

In the README.md file, I have a chart that looks like this:
GDW        | Bootstrap |
|----------|:---------:|
Global     | *-lg.     |
@desktop   | *-md      |
@tablet    | *-sm      |
@mobile    | *-xs      |
@mobile-xs | Global    |

It's a little confusing because the media queries in the theme are desktop first in approach, but Bootstrap uses a mobile first approach. This chart is helpful when using bootstrap's grid classes or the hidden- and visible- helper classes (which is what we will use here).

In a nutshell, just say you want to use the css background image in all viewports except mobile, in which you will want to switch to the <img> tag, you will do the following:

In your css file, in the #banner class where you have your background defined, you will do

@media @mobile {
  background: none;
}

And for the <img> you will add the class visible-xs. What visible-xs does is display: none the element it is on, until it reaches the -xs viewport size and then it will switch to display: block. In the chart above, you can see that corresponds with the @media @mobile size.

As another example, if you wanted to use the css background image but switch it for tablet size and below, you would do the following: 

In your CSS file in the #banner class:

@media @tablet {
  background: none;
}

And on the <img> element, you would add the class visible-xs as well as visible-sm. The reason we need both visible-xs AND visible-sm is because the visible and hidden classes are designed to ONLY work in the viewport size specified. (col classes cascade up though.... so col-sm-3 would also work in md and lg sizes. Very confusing, I know...)

Regarding the Image in your CSS file:
You are very close with this code in that you were trying to put the background image in the css. However, it should not be on banner-img since that's the ID on the <img> element. You need to instead have it on the #banner element. You should never have to set a css background on an <img> since the image is specifically meant for pulling in images into HTML.

Also in this code, you were super close with the max-width on .theme-headline, it just needs to be a little smaller so the text can wrap without the <br> tag. The position: relative and position: absolute can both be removed. Padding can also be added to #banner to help with spacing.

#banner-img {
  background: url('@{path}banner.jpg') center / cover no-repeat;
  position: relative;
  
    .theme-headline {
      position: absolute;
      max-width: 800px;
      padding: 10px 15px;
    }
}


Regarding the Image: 
For the smaller viewports, I cropped the banner image for the switch since the text won't be over it. The name is banner-mobile.jpg but I'll let you make the switch in index.html for the muscle memory. :) 

A note on the text:
We won't be able to use the <br> tag to break text. The reason for this is because when I do the dynamic swap with coldfusion, the text that gets pulled in won't automatically have a <br> tag. What we'll need to do for this is have a defined width or max-width on theme-headline in the banner and that will make the text wrap since the .theme-headline div won't be wide enough.

A note on the theme-bottom-banner stuff:
The content in this section actually is one of GDW's plaform footers so you don't actually need to code this! Yay! (You can kind of see it here except I have a multi-location version on this site: http://www.nikkimorley2.greatmedicalwebsites.com/) This theme doesn't have any content in theme-bottom-banner so you can ignore that entirely. :) You did a lovely job on the HTML though! 
