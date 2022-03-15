# GDW-Themes
Collaborative Build Repo for GDW Themes

## Structure of this Repo
There will be a template folder with all the files needed to build a theme. This template folder will be cloned for each theme with assets and notes added to it. 

## Steps to Get An Environment Running
You will want to use VS Code as your code editor in order to use the Live Server extension.
### Navigate to the Correct Directory
If a directory has not already been set up for your theme, first clone the themeTemplate folder and name it for the theme. In your terminal (or bash or command line depending on your set up), use the `cd` command to change the directory to the parent folder of that theme. 
### Less
If you don't already have less installed on your computer, in your terminal run `npm install -g less` to use node to install less globally. 

Now, in the same terminal, you will want to watch the styles.less file and compile this into styles.css. To do this, run ` lessc styles.less styles.css` in the terminal.

### Spin Up A Server
Make sure you have the Live Server extension installed by Ritwick Dey.

Once installed and enabled, while on the index.html page, go to the lower right of your VS Code window and click the "Go Live" text to spin up a server. A new localhost will appear in your browser.

Alternatively, you can also right click on the index.html file and select "Open with Live Server".

