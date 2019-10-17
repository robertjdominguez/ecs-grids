# Grids!

## Directions

These will serve as our notes in class today. Check off items as we complete them.

## What is a grid?

All html elements have a property called `display` that allows us to change how something is viewed. With this property, we can assign it a value of `grid` to
tell the browser that the element will have a certain number of rows and columns. Using grid makes it super easy to create a website that is responsive -- this means that as the size of the screen changes, the content will adjust to fit it.

## Steps

Follow along with me in class. What I teach you will seem really simple, but it will take some practice to get it right! I'll show you some different properties that are key to getting grid nailed down; from there, you'll have a challenge to complete before you come into class again at the end of the week.

[ ] Start by opening `index START.html` and `main START.css` side-by-side in Atom. Then, open a Firefox window and get `index START.html` open. When your screen is like mine, go half-mast.

### display

[ ] This property can be set to a number of things, but we'll mainly use `grid` as the value -- like so:

```CSS
.container {
    display: grid;
}
```

### grid-template-columns

[ ] Next, we need to tell the browser how many columns our grid should have. This is a long property name called `grid-template-column` -- change it like this:

```CSS
.container {
    display: grid;
    grid-template-columns: 200px 200px 200px;
    grid-gap: 20px;
}
```

### grid-gap

[ ] Without this property, our elements are going to be squished up next to each other without any type of margin. This simply gives a defined gap of space in between each element inside of our grid:

The code above is telling the browser that there should be three columns that are all `200px` wide -- they don't have to be the same! Try changing them around and see what happens.

### fr units

[ ] I love me some fr-units! This is a unit that stands for "free-remaining space" -- essentially, a fraction. Try changing our css to this:

```CSS
.container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
    grid-gap: 20px;
}
```

### repeat function

[ ] How about we write that a little clener? Remember, progrmamers are lazy -- I don't want to have to write `1fr` over and over again! We can use something called a `function` in css. Functions are important in programming languages and are essentially "actions" or do-ers. Instead of writing `1fr` five times, you can just write:

```CSS
.container {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    grid-gap: 20px;
}
```

### minmax and auto-fit

[ ] You may have noticed that while everything fits in nice and neat, it gets really compressed whenever you change the size of your window to something really small. That's because the browser is being told to render the element 1/5 of the remaining space of the window! We can change this around by adding one more bit of css, called a `min-max`. What this does is tell the browswer what's the SMALLEST an element can be, and what's the LARGEST it can be. Try this out:

```CSS
.container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    grid-gap: 20px;
}
```
## Challenge!
Once you've finished this, go back to our `fix-it` repo and change the Altacorp's project page to have three equal columns on larger screens, but automatically resize the project-cards to the whole screen as the window gets smaller.
