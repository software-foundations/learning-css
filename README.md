# learning-css
CSS concepts

## Introduction

- Css means Cascade Style Sheet
- Use class in tags and use class selector in css is strongly recommended
- Classes with less things are easier to be reused
- Tradeoff: generalist class x all responsabilities in only specialized class
- generalist class -> reuse
- specialized class -> component

## CSS Anatomy

- Css is case sensitive for selectors (attributtes) but not for tag selector
- Write css code using dash case pattern
- We must mantein code style (dash or camel) along whole css code!
- Css has predefined values (egg. solid) and functions (egg. rgb)

[index.html](coder/index.html)
[anatomia.html](coder/anatomia.html)

```html
	<div class='my-class'>
		...
	</div>
```

```css
	.my-class{
		color: #000;
		font-size: 4px;
		text-align;

		/* Multiple values */
		border: solid 5px navy; /* shorthand property */

		font-family: Helvetica, sans-serif;

		/* Functions */
		width: calc(100% - 30px); /* 100% of screen; 30px less */
		background-color: rgb(34, 153, 189);
	}

	/* Pseudo classes */
	.my-class:hover {
	    background-color: orangered;
	}

	/* Pseudo elements */
	.seletor::first-letter {
            font-size: 60px;
            font-weight: bold;
        }
```

## Internal, external and inline CSS

[index.html](coder/index.html)
[origem.html](coder/origem.html)
[origem.html](coder/css/externo.css)

- The priority is the other of processing
- Inline has higher priority, but is not recommended use inline css
- Best practice: put css outside html component, in a external file

- Link css tags are declared in head tag
- Link: rel attr: is the relation (acts like type) of the external file linked

```html
	<head>
		<link rel="stylesheet" href=".../externo.css">
	</head>
```

## Creating the .tag class

[index.html](coder/index.html)
[index.html](coder/classeTag.html)
[origem.html](coder/css/tag.css)
[origem.html](coder/js/tag.js)

- The style applyed to a tag is passed to its children tags

Apply style to subset of the selected elements
```css
	[selector] [child selector] {
		...
	}
```

```css
	body {
	    font-size: 40px;
	}

	ul, ol {
	    padding: 0;
	}

	li {
	    margin-left: 60px;
	}

	.tag {
	    border: solid 4px;
	    margin: 5px;
	}

	.tag label {
	    color: #fff;
	    font-size: 25px;
	    vertical-align: top;
	    margin-right: 10px;
	    padding: 0px 5px 3px 3px;
	}
```

## CSS Selectors

[index.html](coder/index.html)
[selectors.html](coder/seletores.html)

- * (all elements in page)
- elem
- .class
- #id
- [attrib]

- :pseudo-class
- ::pseudo-element

Combining selectors
- div + p (ADJACENT sibling)
- div ~ p (GENERAL sibling)

- div > p (child - first child element founded)
- div > p (descendant - all child elements founded)



Tips: 
1. Id is useful to both navigate to anchors and style
2. class is reccomended to apply style to components
3. Work with personalized attrs to work with javascript; classes to style
4. Select an id perform faster than select an attrib

More combined selectors

- [attrib = something]
- [attrib ~= something] -> <tag class = "something something2"></tag>. Childs
- [attrib *= so] -> <tag class = "something something2"></tag>.  Get all *so...
- selector:nth-child(1) -> get selector which is the first child of sthg
- selector > :nth-child(odd) -> get selectors which are the odd children of sthg
- selector > :nth-child(even) -> get selectors which are the even children of...
- It is useful to apply striped style in tables
- selector-1, selector-2, ... -> apply the same style to selector 1, 2 ... elems
- selector > span:nth-of-type(2) -> 2° span element which are child of selector

## CSS specificity

[index.html](coder/index.html)
[especificidade1.html](coder/especificidade1.html)

[mdn](https://developer.mozilla.org/pt-BR/docs/Web/CSS/Specificity)

- The outer element style has priority to its childs styles

Specifities (order of priority):

1. Rule with !important (Don't use this. Its use is discouraged)
2. Selectors more specifics (like inline)
3. Last rule processed

- Notes
1. The more specific style has priority from others
2. A class is more specifc than a tag
3. tag.class selector is more specific than .class selector

[especificidade2.html](coder/especificidade2.html)

[specificity calculator](https://specificity.keegan.st/)

Specificity level
- inline > id > class > attribute

## Inheritance

[index.html](coder/index.html)
[heranca.html](coder/heranca.html)
[google fonts](https://fonts.google.com/)

- Some styles are passed for child elements
- The css highest specificity overrides the other. It is worth for inheritance
- Inline style overrides the inherited style

Css styles that are passed to its children
- font-family

Css styles that aren't passes to its children
- font-size
- border
- padding

- Short hand property (width, style, and color)
```css
	selector{
    	border: solid 3px red;
	}
```

- Inheriting some property explicitly which are not inherited by default
```css
	selector{
		border: inherit;
		padding: inherit;
	}
```

- Explicity inheritance is not widely used.

## Box model

[index.html](coder/index.html)
[box.html](coder/display.html)

- Margin -> Border -> Padding -> Content
- Maring is the distance of the element to the other
- Border is between Margin and Padding
- Padding is the distance of the content to the border
- Content is the content itself

Pagging shorthands
```css
	padding: 5px; /* 5 px of padding in top, right, bottom, and left*/
	margin: 5px; /* 5 px of margin in top, right, bottom, and left*/
	padding-top: 5px; /* 5 px of padding in top*/
	padding: 5px 10px; /* 5 px in top and bottom; 10 in left and right*/
	padding: 1px 2px 3px 4px; /* 1 px in top; 2 in righ; 3 in bottom, 4 in left*/
```

Properties
```css
	selector {
		float: left /* each element concat to the left of each outer elements*/
	}
```

## Margin Collapse

[index.html](coder/index.html)
[margin.html](coder/margin.html)

It is an effect: margins overlap

- Occurs when there's an empty elem between other two not none elem with margin

```css
	padding-bottom: 5px; /* 5 px of padding in bottom*/
```

How to prevent this behavior?
- Absolute position
- inline display: block


## Display Property

[index.html](coder/index.html)
[margin.html](coder/margin.html)

- display block: break line, allows width, heigth;

- display inline: keep line, doesn't allow width, heidth;

- display inline-block: keep line, allows width, heigth
