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
- General Formatting
- Anatomy/Structure
- Selectors
- Properties
- Comments
- Tools

## Folder Architecture
### WIP

## File Names
### WIP

## General Formatting

### Spacing

- Use 4 spaces for indentation. Don't use tab.

- Don't mix spaces and tabs.

- Remove all spaces at the end of the line.

- Use space between the selector and the bracket.

- Use space between property and value.

- Always leave a blank line between rules

### Selectors & Properties

- Write one selector per line

```css
.selector1,
.selector2,
.selector3 {
    property: value;
}
```

- Write one property per line

```css
.selector1 {
	property: value;
    property: value;
}
```

## Anatomy/Structure
### WIP

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

- *Avoid ID selectors* as much as you can.

⋅⋅⋅Declarations defined for an ID selector can't be reused.


