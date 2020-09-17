# CSS

Use [SASS](http://sass-lang.com/).
Styling pattern: [BEM](http://getbem.com/)
If using utility based classes use [Tailwindcss](https://tailwindcss.com/)

---


### Alphabetise

Alphabetise the properties:

```css
#tag {
    background-color: #000
    border: 1px solid #ccc;
    font-size: 22px;
    font-weight: 700;
    height: 120px;
    padding: 10px 20px;
    text-align: center;
    width: 300px;
}
```

### Class and ID Names

Class and ID names should be underscore not camel-case or dashes.
Use underscores becuase it keeps to the same convention as SASS - Identifiers use underscores, where as variables and mixins, etc use dashes.

```css
/* Good - Use underscores */
.this_is_good {}

/* Bad - don't use camel case */
.thisIsBad {}

/* Bad - don't use dashes */
.this-is-bad {}
```

### Indentation

Each indentation level is made up of four spaces. Do not use tabs. All projects will have an `.editorconfig` file, make sure your editor is setup to use it

```css
/* Good */
.tag_name {
	background-color: black;
    color: white;
}

/* Bad - all on one line */
.tag_name {color: #fff; background-color: #000;}
```

Rules inside of `@media` must be indented an additional level.

```css
/* Good */
@media only screen and (max-width:480px) {
   .tag_name {
       color: green;
   }
}
```

### Brace Alignment

The opening brace should be on the same line as the last selector in the rule and should be preceded by a space. The closing brace should be on its own line after the last property and be indented to the same level as the line on which the opening brace is.

```css
/* Good */
.tag_name {
    color: #fff;
}

/* Bad - closing brace is in the wrong place */
.tag_name {
    color: #fff;
    }

/* Bad - opening brace missing space */
.tag_name{
    color: #fff;
}
```

### Property Format

Each property must be on its own line and indented one level. There should be no space before the colon and one space after. All properties must end with a semicolon.

```css
/* Good */
.tag_name {
    background-color: blue;
    color: red;
}

/* Bad - missing spaces after colons */
.tag_name {
    background-color:blue;
    color:red;
}

/* Bad - missing last semicolon */
.tag_name {
    background-color: blue;
    color:red
}
```

### Using CSS Preprocessors (SASS)

Keep nesting to 3 levels deep where possible. 

```scss
/* Good */
.tag_name {
    .inner {
      ...

        .title {
         ....

            .subtxt {
            ...

            }
        }
    }
}

/* Bad - more than 3 levels of nesting */
.tag_name {
    .inner {
      ...

        .title {
         ....

            .subtxt {
                ...

                .element {
                    ...

                }
            }
        }
    }
}
```

Declare `@extend` followed by `@include` statements first in a declaration block.

```scss
/* Good */
.tag_name {
    @extend %padding;
    @include size(100px, 200px);
    color: #555;
    font-size: 11px;
}

/* Bad */
.tag_name {
    color: #555;
    @extend %padding;
    font-size: 11px;
    @include size(100px, 200px);
}
```

### Vendor-Prefixed Properties

No need to include vendor prefoxes, all CSS assets in this project will go through Autoprefixer which will determine which vendor-prefixes to add.
This allows the src files to be minimal and allows developers to focus on the styling and less about browser support.

```css
/* Good */
.tag_name {
    border-radius: 4px;
}
```

```css
/* Bad */
.tag_name {
    -moz-border-radius: 4px;
    -webkit-border-radius: 4px;
    border-radius: 4px;
}
```

### Using !important

Try to not use !important on CSS properties. The only time this is allowed is in a global style.

```css
/* Good */
.tag_name {
   color: red;
}

/* Bad - don't use !important */
.tag_name {
   color: red !important;
}
```

### Font Sizing

All font sizes must be specified using rem only. Do not use percentages, ems or pixels alone.

```css
/* Good */
.tag_name {
   font-size: 1.4rem;
}

/* Bad - uses ems */
.tag_name {
   font-size: 1.2em;
}

/* Bad - uses percentage */
.tag_name {
   font-size: 86%;
}

/* Bad - uses pixel */
.tag_name {
   font-size: 14px;
}
```

### HEX value

When declaring HEX values, use lowercase and shorthand (where possible). The CSS assets are optimised for shorthand, however it is nice to have consistency.

```css
/* Good */
.tag_name {
    color: #ccc;
}

/* Bad */
.tag_name {
    color: #CCCCCC;
}
```

### String Literals

Strings should always use double quotes (never single quotes).

```css
/* Good */
.tag_name:after {
    content: "tag_name";
}

/* Bad - single quotes */
.tag_name:after {
    content: 'tag_name';
}
```

### Background Images and Other URLs

When using a url() value, always use quotes around the actual URL, this helps cases where some characters need to be escaped.

```css
/* Good */
.tag_name {
    background: url("img/logo.png");
}

/* Bad - missing quotes */
.tag_name {
    background: url(img/logo.png);
}
```

### Attribute values in selectors

Use double quotes around attribute selectors.

```css
/* Good */
input[type="submit"] {
    ...
}

/* Bad - missing quotes */
input[type=submit] {
    ...
}

/* Bad - using single quote */
input[type='submit'] {
    ...
}
```


### Do not use units with zero values

Zero values do not require named units, omit the “px” or other unit.

```css
/* Good */
.tag_name {
   margin: 0;
}

/* Bad - uses units */
.tag_name {
   margin: 0px;
}
```

### Selectors

Each selector should appear on its own line. The line should break immediately after the comma. Each selector should be aligned to the same left column.

```css 
/* Good */
button,
input.button {
   color: red;
}

/* Bad - selectors one on line */
button, input.button {
   color: red;
}
```

### :hover and :focus

If :hover pseudo class is styled, :focus should also be styled for accessibility. Focus styles should never be removed.

```css
/* Good */
a:hover,
a:focus {
   color: green;
}

/* Bad - missing :focus */
a:hover {
   color: green;
}
```

### Width and height on components

No heights on anything that contains text. Components should be flexible and their widths should be controlled by grids.

```css
/* Good - no width specified */
.callout_content {
    border: 1px solid #ccc;
    background: #fff;
}

/* Bad - dimension specified */
.callout_content {
    border: 1px solid #ccc;
    background: #fff;
    height: 150px;
    width: 200px;
}
```

### Naming classes

When labelling elements within a component with a class, try to avoid generic classes like `.inner`, `.hd`, `.bd`. Instead, prefix the class name with the name of the component. This is to avoid CSS getting overwritten when classes are too generic.

```css
/* Good */
.box{
    &__hd {
        background: #ccc;
    }
    &__bd {
        background: #ccc;
    }
}

/* Bad */
.box .hd {
    background: #ccc;
}
.box .bd  {
    background: #ccc;
}
```

### Comments

* Comments should be used in CSS to separate the different section in the file, and highlight anything that you or other developers may require at a later date.

## SASS

### Filename convention

All files which do not need to be compiled directly will have an _ [underscore] in front of them. This tells SASS to do nothing with them unless they are imported.


### @extend
The @extend directive can help avoid non-semantic style concerns by telling SASS that one selector should inherit the styles of another selector.
One of the problems with @extend is it will indiscriminately extend every instance of a matching selector that it finds. So if you were extending .foo and it was referenced 5 times, it will extend those 5 references.

The way to work with this is to create a silent class %foo. Example: `.foo, %foo { color: red; }`
A silent class should only ever exist once in any project. This means we can limit the reach of our @extends.

Rules to follow:
* Only write a given silent class once in your SASS.
* Only ever @extend silent classes, unless the class is actually being used for styling.
* Use solid classes in markup, and as many times as you need in your SASS.

A primary example of @extend being used is to extend the silent %clearfix class. We will not add uneccesary markup or classes to elements in the HTML files, we will extend this slient class where it is required in the CSS. This keeps everything tidy and makes it easier to manage.


### @include

@includes should appear above all CSS attributes but below @extends.
You will use @includes mainly to call mixins.


### Easing
There is a variable file called _easing.scss which contains Robert Penner's easing functions converted into cubic-bezier timing functions. These will work with CSS3 transitons.

Here is an example of this being used.

```css
transition: all .5s $easeOutQuart;
```

### Durations
For consistency it is better to use durations in seconds, rather than milliseconds.

```css
/* Good */
.element {
    transition: all .5s $easeOutQuart;
}

/* Bad */
.element {
    transition: all 500ms $easeOutQuart;
}
```

