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