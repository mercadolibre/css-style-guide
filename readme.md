# CSS Style Guide

Mercado Libre CSS Style Guide.

## Table of contents

1. [Introduction](#introduction)
2. [Language](#language)
3. [Whitespace](#whitespace)
4. [Rules](#rules)
5. [Declarations](#declarations)
6. [Selectors](#selectors)
7. [Properties and values](#properties-and-values)
8. [At-rules](#at-rules)
9. [Comments](#comments)
10. [Appendix: Sass](#appendix-sass)
11. [Appendix: Vendor prefixes](#appendix-vendor-prefixes)

## Introduction

This document defines formatting rules and methods for writing stylesheets.
It aims at helping you to author code that is readable, maintainable,
reusable and scalable.

By following this guidelines we are going to:

- Improve code quality.
- Encourage collaboration.
- Reduce time required to understand existing code.
- Increase productivity.
- Maintain our sanity.

*It’s very important to keep in mind that:*

- Consistency is fundamental. Every line of code should appear to be written
  by a single person, no matter the number of contributors and their personal
  preferences.

- Code must be focused on readability and simplicity —even at the cost of
  repetition. Clever code that is hard to understand usually does more harm
  than good.

This guidelines should be learned, understood, and followed at all times.
Any deviation must be fully justified.

## Language

Always write in English: comments, class names, etc. Remember that we are a
multicultural company and not all of us speak the same language.

## Whitespace

- Use Unix newline character: `LF`.
- Use two spaces per indentation level.
- Remove all trailing whitespace.
- Always end files with a newline.
- Use only one blank line as a separator.

```css
/* DON'T */

.foo {¤
——··font-weight: 900;¤
——color: #222;····¤¬
}——¤¬
```

```css
/* DO */

.foo {¬
··font-weight: 900;¬
··color: #222;¬
}¬
¬
```

Make this easier by using this [configuration](.editorconfig) for
[EditorConfig](https://editorconfig.org/). *If you want to understand why
whitespace it’s important you can
[check this presentation](https://speakerdeck.com/battaglr/why-you-should-care-about-whitespace).*

## Rules

- Place the opening brace next to the selector.
- Use one space before the opening brace.
- Place the closing brace in the same column as the first character of a rule.
- Separate each rule by a blank line.

```css
/* DON'T */

.foo
{
  color: #222;
}
.bar{color: #999;}
```

```css
/* DO */

.foo {
  color: #222;
}

.bar {
  color: #999;
}
```

In large blocks of rules that only consist of one selector and one declaration,
a single-line format should be used.

- Use one space after the opening brace.
- Use one space before the closing brace.
- Don’t separate rules by a blank line.
- Don’t align braces.

```css
/* DON'T */

.foo{color: #000;}
.foobar {color: #222;}

.bar    { color: #444; }
.barfoo { color: #666; }
```

```css
/* DO */

.foo { color: #000; }
.foobar { color: #222; }
.bar { color: #444; }
.barfoo { color: #666; }
```

Don’t indent rules with the intention to *replicate* the DOM structure.
This will make your code less flexible and introduce a maintenance burden.

```css
/* DON'T */

.foo {
  color: #222;
}

  .foo__bar {
    color: #444;
  }

    .foo__baz {
      color: #666;
    }
```

```css
/* DO */

.foo {
  color: #222;
}

.foo__bar {
  color: #444;
}

.foo__baz {
  color: #666;
}
```

## Declarations

- Define one declaration per line.
- Place one space after the colon.
- Always end declarations with a semicolon.
- Don’t place spaces before the colon or the semicolon.

```css
/* DON'T */

.foo {
  font-weight:900;
  color : #222 ;
}

.bar {
  padding:10px; margin:0
}
```

```css
/* DO */

.foo {
  font-weight: 900;
  color: #222;
}

.bar {
  padding: 10px;
  margin: 0;
}
```

## Selectors

- Place one selector per line in grouped selectors.
- Quote attribute values using single quotes.

```css
/* DON'T */

.foo, .bar {
  color: #222;
}

.foobar[attr=val] {
  color: #444;
}
```

```css
/* DO */

.foo,
.bar {
  color: #222;
}

.foobar[attr='val'] {
  color: #444;
}
```

### Recommendations

Never use id selectors.

```css
/* DON'T */

#foo {
  color: #222;
}
```

```css
/* DO */

.foo {
  color: #222;
}
```

Avoid type selectors as much as you can.

```css
/* DON'T */

.foo h1 {
  color: #222;
}
```

```css
/* DO */

.foo-heading {
  color: #222;
}
```

## Properties and values

Don’t specify length units for zero values.

```css
/* DON'T */

.foo {
  padding: 0px 20px;
}
```

```css
/* DO */

.foo {
  padding: 0 20px;
}
```

Always specify leading zeros in fractional numbers.

```css
/* DON'T */

.foo {
  top: .25%;
  left: -.5%;
}
```

```css
/* DO */

.foo {
  top: 0.25%;
  left: -0.5%;
}
```

Use lowercase for hexadecimal values, and shorthand notation when allowed.

```css
/* DON'T */

.foo {
  background: #ffffff;
  border-color: #F3F3F3;
}
```

```css
/* DO */

.foo {
  background: #fff;
  border-color: #f3f3f3;
}
```

Quote URL values using single quotes.

```css
/* DON'T */

.foo {
  background: url(../images/image.png);
}
```

```css
/* DO */

.foo {
  background: url('../images/foobar.png');
}
```

Quote font family names that contain whitespace using single quotes.

```css
/* DON'T */

.foo {
  font-family: "Times New Roman", Times, serif;
}
```

```css
/* DO */

.foo {
  font-family: 'Times New Roman', Times, serif;
}
```

Don’t place spaces before the opening parenthesis nor after the closing
parenthesis of a function.

```css
/* DON'T */

.foo {
  width: calc( 20% - 5px );
  background: rgba( 0, 0, 0, 0.6 );
}
```

```css
/* DO */

.foo {
  width: calc(20% - 5px);
  background: rgba(0, 0, 0, 0.6);
}
```

Include a space after each comma in comma-separated values.

```css
/* DON'T */

.foo {
  font-family: 'Times New Roman',Times,serif;
  background: rgba(0,0,0,0.6);
}
```

```css
/* DO */

.foo {
  font-family: 'Times New Roman', Times, serif;
  background: rgba(0, 0, 0, 0.6);
}
```

Long comma-separated set of values should be arranged across multiple lines.

- Place the first set in the same line than the property.
- Place the following set/s in a new line using one extra level of indentation.

```css
/* DON'T */

.foo {
  box-shadow: inset 0 0 4px rgba(17, 17, 17, 0.6), 0 0 8px rgba(0, 0, 0, 0.6);
  background: url('../images/foobar.png') repeat-y,
  url('../images/barfoo.png') repeat-x;
}
```

```css
/* DO */

.foo {
  box-shadow: inset 0 0 4px rgba(17, 17, 17, 0.6),
    0 0 8px rgba(0, 0, 0, 0.6);
  background: url('../images/foobar.png') repeat-y,
    url('../images/barfoo.png') repeat-x;
}
```

### Recommendations

When possible, use shorthand properties.

```css
/* DON'T */

.foo {
  padding-top: 0;
  padding-right: 10px;
  padding-bottom: 20px;
  padding-left: 10px;
}
```

```css
/* DO */

.foo {
  padding: 0 10px 20px;
}
```

Don’t use keyword values when the same result could be achieved using an
explicit value.

```css
/* DON'T */

.foo {
  background: white;
  border-width: medium;
}
```

```css
/* DO */

.foo {
  background: #fff;
  border-width: 4px;
}
```

Never use `!important` to resolve a specificity issue.

```css
/* DON'T */

.foo {
  float: left !important;
}
```

```css
/* DO */

.foo.bar {
  float: left;
}
```

## At-rules

At-rules that directly contain declarations should follow the same pattern that
applies to any other rule.

```css
/* DON'T */

@font-face {
  font-family:Foobar;
  src:local(Foobar),url(../webfonts/foobar.woff) format(woff);
  font-weight:bold;font-style:normal}
```

```css
/* DO */

@font-face {
  font-family: 'Foobar';
  src: local('Foobar'),
    url('../webfonts/foobar.woff') format('woff');
  font-weight: 700;
  font-style: normal;
}
```

Nested rules inside at-rules should be properly indented.

- Don’t leave a blank line before the first rule.
- Don’t leave a blank line after the last rule.

```css
/* DON'T */

@media(min-width:768px){

.foo {
  font-weight: 900;
  color: #222;
}

.bar {
  padding: 10px;
  margin: 0;
}

}
```

```css
/* DO */

@media (min-width: 768px) {
  .foo {
    font-weight: 900;
    color: #222;
  }

  .bar {
    padding: 10px;
    margin: 0;
  }
}
```

## Comments

Use [sentence case](http://en.wiktionary.org/wiki/sentence_case) for all kind
of comments.

```css
/* Single-line comment. */

/**
 * Multi-line comment.
 */
```

*Use native single-line comments when working with Sass.*

```scss
// Single-line comment.

////
// Multi-line comment.
//
```

### Header comments

Use this as a header for every stylesheet.

```css
/**
 * Component name
 * Small description of what the component does, where it’s used, etc.
 */
```

*Use native single-line comments when working with Sass.*

```scss
////
// Component name
// Small description of what the component does, where it’s used, etc.
//
```

### Reference comments

To avoid interfering with the code reading, try to use “reference comments”.

```css
/**
 * 1. Override inherited value.
 * 2. Fallback for browsers that don’t support `rgba()`.
 */

.foo {
  padding: 0; /* 1 */
  background: #222; /* 2 */
  background: rgba(0, 0, 0, 0.6);
}
```

*Use native single-line comments when working with Sass.*

```scss
////
// 1. Override inherited value.
// 2. Fallback for browsers that don’t support `rgba()`.
//

.foo {
padding: 0; // 1
background: #222; // 2
background: rgba(0, 0, 0, 0.6);
}
```

### Tag comments

- The only accepted tag is: `TODO`.
- Use uppercase for the tag name.
- Place a colon after the end of the tag name.
- Place a space after the colon.

```css
.foo {
  /* TODO: add fallback. */
  background: rgba(0, 0, 0, 0.6);
}
```

*Use native single-line comments when working with Sass.*

```scss
.foo {
  // TODO: add fallback.
  background: rgba(0, 0, 0, 0.6);
}
```

### Section comments

When appropriate, break code into meaningful sections.

```css
/* First level
   ---------------------------------------------------------------- */

/* Second level
   -------------------------------------------- */
```

*Use native single-line comments when working with Sass.*

```scss
// First level
// ---------------------------------------------------------------- //

// Second level
// -------------------------------------------- //
```

## Appendix: Sass

### Syntax

Always use the
[SCSS syntax](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#syntax).
This requires the use of the `.scss` file extension.

### Variables

- Use variables —at least— for colors and font size.
- Use `!default` only when a variable it’s likely to be modified.

### At-rules

#### `@import`

- Define one `@import` declaration per line.
- Quote file names using single quotes.
- Don’t include the leading underscore when importing a *partial*.
- Don’t include the `.scss` file extension.

```scss
// DON'T

@import "_foo.scss", "_bar.scss";
```

```scss
// DO

@import 'foo';
@import 'bar';
```

#### `@mixin`

Use a `@mixin` whenever you want to generate reusable sections of code.

#### `@extend`

Avoid using `@extend`. Try to use a `@mixin` instead.

### Nested rules

- Only use nesting when absolutely necessary.
- Never nest more than three levels deep.
- Separate each nested rule by a blank line.

```scss
// DON'T

.foo {
  color: #000;
  .bar {
    color: #222;
    .baz {
      color: #444;
      .qux {
        color: #666;
        .quux {
          color: #999;
        }
      }
    }
  }
}
```

```scss
// DO

.baz {
  color: #444;

  .qux {
    color: #666;

    .quux {
      color: #999;
    }
  }
}
```

Never nest inside empty rules.

```scss
// DON'T

.foo {
  .bar {
    color: #222;
  }
}
```

```scss
// DO

.foo .bar {
  color: #222;
}
```

Never generate compound names using the parent selector.

```scss
// DON'T

.foo {
  color: #000;

  &__bar {
    color: #222;
  }

  &--baz {
    color: #444;
  }
}
```

```scss
// DO

.foo {
  color: #000;
}

.foo__bar {
  color: #222;
}

.foo--baz {
  color: #444;
}
```

## Appendix: Vendor prefixes

Never use vendor prefixes directly in the source code.

- Use [Autoprefixer](https://github.com/postcss/autoprefixer).
- If Autoprefixer is not available, you could use a `@mixin`.

### Exceptions

When certain property is non-standard, Autoprefixer will not perform any action.

In those situations always leave a comment explaining why you’re using that
property; this will generate code easier to understand and prevent
accidental removals.

```scss
// DON'T

.foo {
  color: #000;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
```

```scss
// DO

////
// 1. Modify default font smoothing mode. Non-standard properties;
//    explicit use of vendor prefixes is required.
//

.foo {
  color: #000;
  -webkit-font-smoothing: antialiased; // 1
  -moz-osx-font-smoothing: grayscale; // 1
}
```

## Contributing

Contributions are welcome!

This project is possible thanks to these
[contributors](https://github.com/mercadolibre/css-style-guide/graphs/contributors)
and many other awesome people!

## License

© 2013-2019 Mercado Libre. Licensed under the [MIT license](license).
