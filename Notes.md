# Notes for this SCSS Learning

Writing things out really solidifies things in the working memory so that's the plan here.

## Using SCSS 

I have already been familiar with the SCSS Compiler plugin on VSCODE but I did learn a new way here!

Here are the steps to use Sass/SCSS with node.js and npm package through it.

1. sudo npm i -g sass

```sudo``` makes the install global along with ```-g``` this will give us global access to sass commands.

2. sass --watch scss/style.scss 

We want sass to watch for the sass file, so we use the ```--watch``` command and tell it where the scss file is ```scss/style.scss``` next we tell it the output css file, ```css/style.css```.

Now if we change anything, since it's watching the file it will compile any new changes into css.

## Don't touch the CSS file when dealing with Sass

The CSS file is going to be continually updated from the SCSS file, there's no point to ever touch the css file and it should be avoided.