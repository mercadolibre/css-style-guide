# CSS Style Guide

MercadoLibre CSS Style Guide.

## Intro
The main goal of this guide is to set standards for writing our CSS files and modules, helping the readability and maintainability of our code. By doing this, we can significantly reduce the time required to understand any front-end implementation.

By writing clean code, we are able to:

- achieve a code that’s easier to understand;
- detect errors and potential problems;
- easily identify what code can be reused;
- build or update any functionality on any code already implemented;
- work on any file regardless of who wrote it.

> "Consistent code, even when written by a team, should look like one person wrote it."
by [Addy Osmani](http://addyosmani.com/blog/javascript-style-guides-and-beautifiers/)

## Table of contents

- Folder Architecture 
- File Names
- [General Formatting](#general-formatting)
- Anatomy/Structure
- [Selectors](#selectors)
- [Properties](#properties)
- [Comments](#comments)
- Tools

## Folder Architecture

	(WIP)

## File Names

	(WIP)

## General Formatting

### Spacing

- Use 4 spaces for indentation. Don't use tab.


- Don't mix spaces and tabs.


- Remove all spaces at the end of the line.


- Use space between the selector and the bracket.


- Use space between property and value.


- Always leave a blank line between rules



### Selectors & Properties

- Write one selector per line.

	```css
	/* DO */
	.selector1,
	.selector2,
	.selector3 {
	    property: value;
	}
	```


- Write one property per line.

	```css
	/* DO */
	.selector1 {
		property: value;
	    property: value;
	}
	```


## Anatomy/Structure
	
	(WIP)


## Selectors

- Only in English. 


- Separate words with Hyphen. Don't use camelCase or underline.

	```css
	/* DON'T */
	.homePage
	.box_registracion
	```

	```css
	/* DO */
	.home-page
	.registration-box 
	```


- Use app-prefixes ONLY for cross-application stylesheets or reusable widgets.

	```css
	/* DON'T */
	.cho-header
	.myml-sales
	```

	```css
	/* DO */
	.commons-header
	.ml-footer
	```


- **Avoid ID selectors** as much as you can.

	_Declarations defined for an ID selector can't be reused._


- Avoid tag selectors unless is for extending another selector.

	_Tag selectors are not specific enough._


## Properties

- Alphabetize declarations.


- Whenever possible, use shorthands.

	```css
	/* DON'T */
	.selector {
		padding-bottom: 2em;
		padding-left: 1em;
		padding-right: 1em;
		padding-top: 0;
	}
	```

	```css
	/* DO */
	.selector {
		padding: 0 1em 2em;
	}
	```


- Omit unit specification when value is "0".

	```css
	/* DON'T */
	margin: 0em;
	padding: 0px;
	```

	```css
	/* DO */
	margin: 0;
	padding: 0;
	```


- Omit the "0" when value is between 0 and 1.

	```css
	/* DON'T */
	margin: 0.5em;
	```

	```css
	/* DO */
	margin: .5em;
	```

- Use Hexadecimal code for colors. 

	_(aca falta cuantos caracteres)_

- Use rgba for background colors.
	
	_Take advantage of the opacity feature._

- Always use `;` at the end of every declaration.

- Don't use `!important`.

## Comments

- All your code should be documented.

- Use single-line comment to add hints, notes, suggestions or warnings.

### Comments types

- **Component header**

	Use this as a header for every stylesheet or component

	```css
	 /**
	  * Component Name
	  * @authors: pmontesano, hmammana, ndevalle
	  * @description: small description of what the component does, where is used, etc.
	  */
	```

- **Block separator**

	Use this format for meaningful separations of code.

	```css
	/* Sidebar
	---------------------------------------------------------------*/
	```

- **Inline comment**

	Use regular comment formatting for small descriptions of properties or rules.

	```css
	.ch-price {
    	line-height: 1em; /* 16px */
	}
	```

	Always comment values that might seem "[magic](https://github.com/csswizardry/CSS-Guidelines#magic-numbers-and-absolutes)":

	```css
	.form-actions {
	    margin-left: 175px; /* label width + 15px */
	}
	```

	And properties that apparently make no sense:

	```css
	.payment-methods {
	    display: inline-block;
	    height: 20px; /* default value, exceptions added to each logo */
        text-align: left; /* just in case the container has text-align:right */     
	}
	```






## Tools

	(WIP)


## License

Licensed under the MIT license.

Copyright (c) 2013 MercadoLibre, http://www.mercadolibre.com/
