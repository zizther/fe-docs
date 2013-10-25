# HTML

			
This document's primary motivation is two- fold: 1) code consistency and 2) best practices. By maintaining consistency in coding styles and conventions, we can ease the burden of legacy code maintenance, and mitigate risk of breakage in the future. By adhering to best practices, we ensure optimized page loading, performance and maintainable code.

## General Guidelines

* For all code languages, using tab (4 spaces)indentation.
* There is no need to compress HTML.
* Start any project using HTML5. Make sure you understand meaning and use of the new tags, read the documentation!
* Lowercase should be used throughout.
* Underscore should be used for classes and unique identifiers; no dashes or camel-casing.
* Place all style images in the 'graphics' directory.
* Try to keep HTTP request down to a minimum.
* Always optimise images for web. Optmise them using a program like Codekit or use something like [smushit.com](http://www.smushit.com) (provided by Yahoo!).
* Google analytics should be placed before ``</head>``.
* Where possible, use other CDNs to deliver content, such as Google code to delivery jQuery.
* Make favicon small and cacheable.
* Minimize the number of iframes.
* Don't scale images in HTML, unless they are responsive, do not use oversized images though.
* Optimise images; some images can be exported smaller as a .png over a .jpg. Look to see what is best.
* Use .png over .gif
* Avoid empty image ``src=""`` tags.
* Conditional Comments can be used, but not because you’re lazy.
	
```html
<!--[if IE]>  <![endif]-->
```
	
* Place suitable title and alt tags on links and images. Do not leave them blank.
* Make sure to add the description tag. Don’t leave it empty (but don’t fill it with useless gunk either).


## HTML5


#### Doctype
A proper Doctype which triggers standards mode in your browser should always be used. Quirks mode should always be avoided.

A nice aspect of HTML5 is that it streamlines the amount of code that is required. Meaningless attributes have been dropped, and the DOCTYPE declaration has been simplified significantly. Additionally, there is no need to use CDATA to escape inline JavaScript, formerly a requirement to meet XML strictness in XHTML.

```html
<!DOCTYPE html>
```

#### Character Encoding

All markup should be delivered as UTF-8, as its the most friendly for internationalization. It should be designated in both the HTTP header and the head of the document.

Setting the character set using <meta> tags.

```html
<meta charset="utf-8">
```


## Markup Guidelines

* Use actual ``<p>`` elements for paragraph delimiters as opposed to multiple ``<br>`` tags.
* Make use of ``<dl>`` (definition lists) and ``<blockquote>``, when appropriate.
* Items in list form should always be housed in a UL, OL, or DL, never a set of ``<div>`` or ``<p>`` tags.
* Use label fields to label each form field, the ``for=""`` attribute should associate itself with the input field ``id=""``, so users can click the labels. cursor: pointer; on the label is wise, as well.
* Do not use the size attribute on your input fields. The size attribute is relative to the font size of the text inside the input. Instead use css width.
* Place an html comment on some closing div tags to indicate what element you're closing. It will help when there is lots of nesting and indentation.
```html
<!-- / #tag_name -->
<!-- / .tag_name -->
```
* Only use one ``<h1>`` tag per page.
* Always use title-case for headers and titles. Do not use all caps or all lowercase titles in markup, instead apply the CSS property ``text-transform: uppercase/lowercase``.
* Place id's and class's before any other attribute on an element.
```html
<input class="form_input" id="name" name="name" type="text" value="">
```
* Tables shouldn't be used for page layout.
* Make use of ``<thead>``, ``<tbody>``, and ``<th>`` tags (and Scope attribute) when appropriate. 
```html
<table summary="This is a chart of year-end returns for 2005.">
	<thead>
		<tr>
			<th scope="col">Table header 1</th>
			<th scope="col">Table header 2</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>Table data 1</td>
			<td>Table data 2</td>
		</tr>
	</tbody>
</table>
```

#### Quoting Attributes

* The HTML5 specification defines quotes around attributes as optional. For consistency with attributes that accept whitespace, all attributes should be quoted. 
* Use double quotation marks (" ") rather than single (' ') for attribute values where necessary.
```html
<p class="line note" data-attribute="106">This is my paragraph of special text.</p>
```


## CSS

#### General Coding Principles

* Add CSS through external files, minimizing the # of files, if possible. It should always be in the HEAD of the document.
* Put style sheets at the top in ``<head>``.
* Use the ``<link>`` tag to include, never the @import.
* Don't include styles inline in the document, either in a style tag or on the elements. It's harder to track down style rules.

#### Prevent Compatibility Mode

Sometimes IE can have a mind of its own and will switch to compatibility mode without you knowing. Include the following in the site <head> to prevent your site from defaulting to compatibility mode:
```html
<meta http-equiv="X-UA-Compatible" content="IE=edge">
```


## CSS Box Model

Intimate knowledge and understanding of the CSS and browser-based box model is necessary for conquering the fundamentals of CSS layouts.


## Web Typography

#### @font-face

The @font-face at-rule allows you to define custom fonts. It was first defined in the CSS2 specification, but was removed from CSS2.1. Currently, it's a draft recommendation for CSS3.

When using @font-face it's recommended to declare the source for each font format. This is important if you want it to work in the most number of browsers, though it is not a requirement for use.

The font formats included in the specification are:

* **woff**: WOFF (Web Open Font Format)
* **ttf**: TrueType
* **ttf, otf**: OpenType
* **eot**: Embedded OpenType
* **svg, svgz**: SVG Font

[Bulletproof @font-face](http://www.fontspring.com/blog/further-hardening-of-the-bulletproof-syntax)

Use either Typekit or Google WebFonts over Cufon or Scalable Inman Flash Replacement (sIFR).




## JavaScript


## Accessibility

The HTML mark-up should comply with [UK web accessibility law](http://www.rnib.org.uk/professionals/webaccessibility/lawsandstandards/Pages/uk_law.aspx) and should follow the [Web Content Accessibility Guidelines](http://www.w3.org/WAI/intro/wcag) as closely as possible.

[W3C checklist of checkpoints for accessibility](http://www.w3.org/TR/WCAG10/full-checklist.html)