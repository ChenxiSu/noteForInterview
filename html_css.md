#html
```
Do not ommit these things

<!DOCTYPE html>
<html lang="en-US">
<head>
  <meta charset="UTF-8">
  <title>HTML5 Syntax and Coding Style</title>
  <link rel="stylesheet" href="styles.css">
</head>
```
#CSS

##Em
Another way of setting the font size is with em values. The size of an em value is dynamic. When defining the font-size property, an em is equal to the size of the font that applies to the parent of the element in question. If you haven't set the font size anywhere on the page, then it is the browser default, which is often 16px. So, by default 1em = 16px, and 2em = 32px. If you set a font-size of 20px on the body element, then 1em = 20px and 2em = 40px. Note that the value 2 is essentially a multiplier of the current em size.

##Box Model
In a document, each element is represented as a rectangular box. Determining the size, properties — like its color, background, borders aspect — and the position of these boxes is the goal of the rendering engine.
###box-sizing
**border-box**:make sure padding and boarder won't add space to width

box-sizing:border-box works so well that people always want to make it default

```
\* {
  -webkit-box-sizing: border-box;//safari
  
     -moz-box-sizing: border-box;//firefox
     
          box-sizing: border-box;
}
```

##clear
Clear:both;

Floating element with clear: moved down but with collapsing effect.

Non-floating element with clear: moved down without collapsing effect.

##Div with everything inside floating
Basically this div is not gonna have any height unless you give one to it. Cause all floating elements do not extend the space inside that div



##position:relative, absolute, fixed or sticky.

###static
This keyword lets the element use the normal behavior, that is it is laid out in its current position in the flow.  The top, right, bottom, left and z-index properties do not apply.

###relative
This keyword lays out all elements as though the element were not positioned, and then adjust the element's position, without changing layout (and thus leaving a gap for the element where it would have been had it not been positioned).

```
<div class="box" id="one">One</div>
<div class="box" id="two">Two</div>
<div class="box" id="three">Three</div>
<div class="box" id="four">Four</div>
```
css

```
.box { 
   display: inline-block; 
   background: red; 
   width: 100px; 
   height: 100px; 
   float: left; 
   margin: 20px; 
   color: white; 
}

#two { 
   position: relative; 
   top: 20px; 
   left: 70px; 
}

```
Elements that are positioned relatively are still considered to be in the normal flow of elements in the document.

An element that is positioned absolutely is taken out of the flow and thus takes up no space when placing other elements. 

###absolute
Do not leave space for the element. Instead, position it at a specified position relative to its closest positioned ancestor if any, or otherwise relative to the initial containing block. Absolutely positioned boxes can have margins, and they do not collapse with any other margins.

***The absolutely positioned element is positioned relative to nearest positioned ancestor (non-static). If a positioned ancestor doesn't exist, the initial container is used.***

absolute is the trickiest position value. absolute behaves like fixed except relative to the **nearest positioned ancestor** instead of relative to the viewport. **If an absolutely-positioned element has no positioned ancestors, it uses the document body, and still moves along with page scrolling.** Remember, a "positioned" element is one **whose position is anything except static**.

###fixed
Fixed positioning is similar to absolute positioning, with the exception that the element's containing block is the viewport. This is often used to create a floating element that stays in the same position even after scrolling the page.

###left/right/top/bottom
These are for positioned elements

##float
Float is intended for wrapping text around images.

The clear property is important for controlling the behavior of floats.It will move the div down to the float element

##display
display is CSS's most important property for controlling layout.Every element has a default display value depending on what type of element it is. The default for most elements is usually block or inline. A block element is often called a block-level element. An inline element is always just called an inline element.

###block-level elements
 Other common block-level elements are div, p and form, and new in HTML5 are header, footer, section, and more.
###inline
 span, a
###inline-block
inline-block elements are like inline elements but they can have a width and height. I guess image belongs to this
###none
display:none won't  take up any space while visibility:hidden will still take up space

###percent width
Percent is a measurement unit relative to the containing block. It's great for images

##flexbox
Flexbox is born to do layout, check the following examples

```
.container {
  display: -webkit-flex;
  display: flex;
}
.initial {
  -webkit-flex: initial;
          flex: initial;
  width: 200px;
  min-width: 100px;
}
.none {
  -webkit-flex: none;
          flex: none;
  width: 200px;
}
.flex1 {
  -webkit-flex: 1;
          flex: 1;
}
.flex2 {
  -webkit-flex: 2;
          flex: 2;
}
```

also

```
.vertical-container {
  height: 300px;
  display: -webkit-flex;
  display:         flex;
  -webkit-align-items: center;
          align-items: center;
  -webkit-justify-content: center;
          justify-content: center;
}
```
##overflow

##floating
The float CSS property specifies that an element should be taken from the normal flow and placed along the left or right side of its container, where text and inline elements will wrap around it.

As mentioned above, when an element is floated it is taken out of the normal flow of the document. It is shifted to the left or right until it touches the edge of its containing box or another floated element.

##selector tricks
###element+element
Assume e1+e2, will Select e2 that are placed immediately after e1.
###first-child
div:first-child
div p:first-of-type will select the first occurence of this type, no matter it is the first element in div or not.

##margin collapse
[Click to see details in MDN]
(https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Mastering_margin_collapsing)

**Adjacent siblings**

The margins of adjacent siblings are collapsed (except when the later sibling needs to be cleared past floats). 

**Parent and first/last child**

If there is no border, padding, inline content, or clearance to separate the margin-top of a block from the margin-top of its first child block, or no border, padding, inline content, height, min-height, or max-height to separate the margin-bottom of a block from the margin-bottom of its last child, then those margins collapse. The collapsed margin ends up outside the parent.

**Empty blocks**
If there is no border, padding, inline content, height, or min-height to separate a block's margin-top from its margin-bottom, then its top and bottom margins collapse.

##center
###vertical-align
The vertical-align CSS property specifies the vertical alignment of an inline or table-cell box.

[see details here](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align)

##Specificity
The following list of selector types is by increasing specificity:

Type selectors (e.g., h1) and pseudo-elements (e.g., :before).
Class selectors (e.g., .example), attributes selectors (e.g., [type="radio"]) and pseudo-classes (e.g., :hover).
ID selectors (e.g., #example).
Universal selector (*), combinators (+, >, ~, ' ') and negation pseudo-class (:not()) have no effect on specificity. (The selectors declared inside :not() do, however.)

Inline styles added to an element (e.g., style="font-weight:bold") always overwrite any styles in external stylesheets and thus can be thought of as having the highest specificity.


[details in MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity)