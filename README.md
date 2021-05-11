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