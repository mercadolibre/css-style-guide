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
- [General Formatting](#formatting)
- Anatomy/Structure
- [Selectors](#selectors)
- [Properties](#properties)
- Comments
- Tools

## Folder Architecture

	(WIP)

## File Names

- Css base: base.css (all clases and elements commons of the project)


- Don't use project's name for css base. 

	/* DON'T */ 
	sales.css

	/* DO */
	base.css	


- Lowercase names and scripted the medium as separator.  

	/* DON'T */
	baseIe7.css	

	/* DO */
	base-ie7.css


- Component names from more than one word. 
	
	/* DON'T */
	paymentMethods.css	

	/* DO */
	payment-methods.css



- Name the components by name.  
	
	/* DO */
	bookmarks.css


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

- Comment whenever necessary to explain the code.


- Comment a property if required.


- Comment magic numbers (values ​​with no apparent sense, explain how you arrived at that number) 


- No prefixes Comment


## Tools

	(WIP)


## License

Licensed under the MIT license.

Copyright (c) 2013 MercadoLibre, http://www.mercadolibre.com/
