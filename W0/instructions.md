# W0: HTML/CSS

## Plain Texts

* #### Titles (will be bold)

Use \<h1>, or \<h2> \<h3> ... for smaller titles.

* #### Paragraphs

Use \<p>

* #### Link

Use \<a href="URL">Description\</a>

* #### Image

Use \<img src="DIR" />

* #### List

Use \<ol>\</ol> for ordered lists, and \<ul>\</ul> for unordered.

Use \<li>\</li> for list items.

* #### Navigation Bar

Use \<nav>\</nav>. Add elements like \<h1> between them.

## Styles

* #### Link .css to .html

Include a 
```html
<link rel="stylesheet" href="filename.css" />
```
in the \<head> section.

* #### Rule
```css
selector {        
    property: value;
}
```

Like, to set a style for all divs. 
```css
div {
    color: red;
    font-family: Arial;
    font-size: 24pt;
}
```

Or, the selector can be ".className" or "#ID" for those with the same class names or IDs. 
```html
<div class="class1">
``` 
or 
```html
<div id="id1">
```

* #### Font Family

Imported from Google Font, to styles.css
```css
@import url("https://fonts.googleapis.com/css?family=Open+Sans:300,600");
```
Then you can modify the font property.
```css
font-family: "Open Sans", sans-serif;
```
The sans-serif is a backup choice, in case Open Sans is not available.

* #### Font Size, Weight

Just
```css
font-size:; & font-weight:;
```

* #### Distance to Margins

We have
```css
margin-top:; & margin-right:; & margin-bottom:; & margin-left:;
```
It has an order of multiple values. Top 1; Right 1,2; Bottom 1,2,3; Left 1,2,4.

The latest in its range will be its value. For example,
```css
margin: 10px 20px 30px 
```
will set the margin to top 10px; right 20px; bottom 30px; left, since the 4th is not available, 20px.
> What a "margin" is? Refer to the Concepts part.

* #### Rounding the Corners
Use
```css
border-radius: num px;
```

## Skills

* #### Utility Class

Use some classes for specific purposes like being red or centering.

```css
.u-textCenter {
    text-align: center;
}

.u-textRed {
    color: red;
}
```

Then you can use it in your elements. Like 
```html
<div class="u-textCenter u-textRed>"
```

* #### Variables

```css
:root {
  --primary: #396dff;
}
```
This is actually not applied to any elements. Just defining the variables, in :root.

```css
color: var(--primary);
```
And you're now using the variable.

* #### Flexbox

A flexible box. Enable via
```css
display: flex;
flex-direction: row | column;
```
The default mode is to arrange by row, or |item1|item2|item3|...

- flex-basis: the inital size of a flex item on the main axis. Can be auto, to change its size automatically.

- flex-grow: the proportions of how the left-over space will be allocated to items in the flexbox. The default is 0, so won't allocate the space unless some item's flex-grow is not 0.

KEEP IN MIND, the items will defaultly have an initial size based on its content. So if you want to split a box into two items of the same size, use
```css
flex-grow: 1;
flex-basis: 0;
``` 

## Concepts

* #### Box Model

![Illustration](https://cloud2data.com/wp-content/uploads/2023/02/Box-Model.png)

So the most inner part is the Content, with a visual (or not) Border around it. 
Padding decides where the Content will be located within the Border. 
Margin decides the relative positioning of this Box Model with respect to other Box Models.

## Example

* #### A perfect image circle

Note that the image is not a square, so it is incorrect to just radius 50%.

First set a container

```css
.avatarContainer {
    padding: 0 35%;
}
```

```css
avatar {
  /* make it responsive */
  max-width: 100%;
  width: 100%;
  height: auto;
  display: block;
  /* div height to be the same as width*/
  padding-top: 100%;

  /* make it a circle */
  border-radius: 50%;

  /* Add image */
  background-image: url("cat.png");

  /* Centering on image`s center*/
  background-position-y: center;
  background-position-x: center;
  background-repeat: no-repeat;

  /* it makes the clue thing, takes smaller dimension to fill div */
  background-size: cover;

  /* it is optional, for making this div centered in parent*/
  margin: 0 auto;
}
```