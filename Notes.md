# Notes for this SCSS Learning

Writing things out really solidifies things in the working memory so that's the plan here.

## Using SCSS without a VSCode Plugin

I have already been familiar with the SCSS Compiler plugin on VSCode but I did learn a new way here!

Here are the steps to use Sass/SCSS with node.js and npm package through it.

1. sudo npm i -g sass

```sudo``` makes the install global along with ```-g``` this will give us global access to sass commands.

2. sass --watch scss/style.scss 

We want sass to watch for the sass file, so we use the ```--watch``` command and tell it where the scss file is ```scss/style.scss``` next we tell it the output css file, ```css/style.css```.

Now if we change anything, since it's watching the file it will compile any new changes into css.

## Don't touch the CSS file when dealing with Sass

The CSS file is going to be continually updated from the SCSS file, there's no point to ever touch the css file and it should be avoided.

## SCSS Tricks

The ```lighten()``` or ```darken()``` modules can make future color changes dynamic even if you have sub colors that are dependant on the changing color.

So say ```$primary-color``` is changed, and you have a button that is primary color but a little lighter. It wouldn't work if its not tied to the variable, but you can tie it to the variable with a ```lighten($primary-color, 10%)``` module usage.

## SCSS Functions

Use the syntax exactly the same as named declared functions with JavaScript except with an ```@``` symbol preceding the word ```function``` and a ```%``` sigil before every parameter.

```
@function darken-text-color($color){
    @return darken($color, 20%);
}
```

Conditionals in SCSS like the if statement also use the same syntax as JavaScript.

```
@if(){
}
@else if(){
}
@else{
}
```

Functions MUST have a ```@return``` value.

## Mixins

Are like functions but they don't return a value.

They allow the making of a group of declarations, once created they can easily be mixed in anywhere else in the scss file. To keep the code writing dry.

Just declare a class, then use ```@extend .classname``` to extend capabilities of the declared class within another.


## Looping

Similar to a loop in JavaScript, but a little different.

```@each``` starts the loop.
```$variable``` will hold that index value of a list.
```in``` is like a ```for... of``` loop keep word ```of```.
```$iterable_list``` is the list to be looped through.

It also looks like lists are declared with ```()``` rather than brackets.

```
// Margin & padding classes
$spaceamounts: (1,2,3,4,5);

@each $space in $spaceamounts {
    .m-#{$space}{
        margin: #{$space}rem;
    }
    .my-#{$space}{
        margin: #{$space}rem 0;
    }
    .mx-#{$space}{
        margin: 0 #{$space}rem;
    }
    .p-#{$space}{
        padding: #{$space}rem;
    }
    .py-#{$space}{
        padding: #{$space}rem 0;
    }
    .px-#{$space}{
        padding: 0 #{$space}rem;
    }
}
```