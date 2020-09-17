# HTML

			
This document's primary motivation is two- fold: 1) code consistency and 2) best practices. By maintaining consistency in coding styles and conventions, we can ease the burden of legacy code maintenance, and mitigate risk of breakage in the future. By adhering to best practices, we ensure optimized page loading, performance and maintainable code.

---

## General Guidelines

* For all code languages, using tab (4 spaces) indentation.
* There is no need to compress HTML.
* Start any project using HTML5. Make sure you understand meaning and use of the new tags, read the documentation!
* Lowercase should be used throughout.
* Underscore should be used for classes and unique identifiers; no dashes and definitely no camel-casing.
* Place all style images in the 'graphics' directory.
* Try to keep HTTP request down to a minimum.
* Always optimise images for web.
* Google analytics should be placed before `</head>`.
* Where possible, use other CDNs to deliver content, such as Google code to delivery jQuery.
* Make favicon small and cacheable.
* Minimize the number of iframes.
* Don't scale images in HTML, unless they are responsive, do not use oversized images though.
* Optimise images; some images can be exported smaller as a .png over a .jpg. Look to see what is best.
* Use .png over .gif
* Avoid empty image `src=""` tags.
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

* Use actual `<p>` elements for paragraph delimiters as opposed to multiple `<br>` tags.
* Make use of `<dl>` (definition lists) and `<blockquote>`, when appropriate.
* Items in list form should always be housed in a UL, OL, or DL, never a set of `<div>` or `<p>` tags.
* Use label fields to label each form field, the =`for=""` attribute should associate itself with the input field `id=""`, so users can click the labels. cursor: pointer; on the label is wise, as well.
* Do not use the size attribute on your input fields. The size attribute is relative to the font size of the text inside the input. Instead use css width.
* Place an html comment on some closing div tags to indicate what element you're closing. It will help when there is lots of nesting and indentation.
`<!-- / #tag_name -->` and `<!-- / .tag_name -->`
* Only use one `<h1>` tag per page.
* Always use title-case for headers and titles. Do not use all caps or all lowercase titles in markup, instead apply the CSS property `text-transform: uppercase/lowercase`.
* Place id's and class's before any other attribute on an element.
`<input class="form_input" id="name" name="name" type="text" value="">`
* Tables shouldn't be used for page layout.
* Make use of `<thead>`, `<tbody>`, and `<th>` tags (and Scope attribute) when appropriate. 


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

* Add CSS through external files, minimizing the number of files, if possible.
* Put stylesheets at the top in `<head>`.
* Use the `<link>` tag to include, never the @import.
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

* **woff2**: WOFF2 (Web Open Font Format)
* **woff**: WOFF (Web Open Font Format)
* **ttf**: TrueType
* **ttf, otf**: OpenType
* **eot**: Embedded OpenType
* **svg, svgz**: SVG Font

If you are only supporting modern browsers, the you will only require the WOFF formats.

It is also ideal to support `font-display: swap;` within your @font-face.

When using Use either Typekit or Google WebFonts, `font-display: swap;` is handled by default now.


## Accessibility

The HTML mark-up should comply with [UK web accessibility law](https://www.gov.uk/guidance/accessibility-requirements-for-public-sector-websites-and-apps) and should follow the [Web Content Accessibility Guidelines](https://www.w3.org/WAI/standards-guidelines/wcag/) as closely as possible.

[W3C checklist of checkpoints for accessibility](http://www.w3.org/TR/WCAG10/full-checklist.html)


## Performance

As we continue to push the limits of what the web can do, it remains just as important a web page can be used with minimal effort or wait time. The main points to focus on are user experience and user perception.

#### Optimize Delivery of CSS and JavaScript

There are many optimisations that should be done for serving CSS and javascript in production:

* Optimse images for web.
* Set caching headers appropriately.
* Consider a cookie-less subdomain for static assets
* Avoid inline `<script>` blocks. They block rendering and are quite devastating to page load time.
* Avoid calling JS function inline.
* CSS should be located in the `<head>` of the document, Javascript should be right before the `</body>` tag.
* Both CSS and JavaScript should be served minified.
* Both should be served using gzip on the wire.
* Reduce the number of HTTP requests, with the use of HTTP/2 we can be a little more lenient towards having multiple assets file

#### Optimize JavaScript execution

During a page load, there is typically a lot of script waiting to execute, but you can prioritise it. This order prioritizes based on user response:

1. Script that changes the visible nature of the page needs to fire absolutely first. This includes any font adjustment or box layout.
2. Page content initialization.
3. Page header, top nav and footer initialisation.
4. Attaching event handlers.
5. Omniture, Doubleclick, and other 3rd party scripts.

#### Shard resources across domains

*Note* With HTTP/2 we don't need to worry about domain sharding, as it does not block head of line.

*Reference for HTTP/1.1*
Static content should certainly be served from a domain different than the one that serves HTML. This is optimal so that there are no extra cookies headers on all static content requests. It's also much easier to write caching rules for the entire domain. (Also any subdomains of the current domain will inherit domain cookies, so it's worth using a completely new domain).

However with enough assets (especially images) the number of requests grows enough to slow down the load of the page. Many browsers have a low constraint of how many assets they will download simultaneously per domain. (In IE6 and 7, it's only two). In this case, we can serve the assets from multiple subdomains such as:

    static1.otherdomain.com
    static2.otherdomain.com
    static3.otherdomain.com
    
#### Avoid IFRAMEs

Iframes are the most costly element to add to a given page. They block the page from firing the onload event until they are complete. Sometimes they are useful to let another agency handle tracking scripts. For example the Doubleclick floodlight tag is an iframe, and the admin can add tracking pixels into it from their dashboard. In any case where an iframe is added, it should be appended to the DOM dynamically after window onload has fired.

#### Measure performance during QA

QA teams should also prioritize performance related tickets alongside visual, functional, and usability issues. Developers and QA should determine how that priority will be assigned. During QA, the success metrics should be tested regularly.

When performance goals aren't met, there are three options:

* Redevelop the code - profile, discover bottlenecks, refactor code, optimize to target faster execution in the browser.
* Drop the feature - turn it off for slower browsers only.
* Redesign approach of the UI - perhaps the design could use a tweak which would bypass the issue entirely.

#### Browser Testing and Support

Today's audience can choose from quite a large pool of web browsers, each providing a slightly (or dramatically) different experience. As developers, it is our responsibility to choose just how the web pages we build are displayed to those users.

#### Search Engine Optimization

An essential part of good web design and development is SEO. Well-structured code is the key to ensuring that a web page not only gets properly indexed by search engines, but made accessible to those with limited web capabilities as well.

##### Be aware of SEO best practices

* Print CSS best practices.
* Site/app will fit according to Browser Resolution guidelines.
* Site/app will be compatible with browser requirements described in Browser Testing and Support.
* Be aware of Accessibility best practices, such as the 508 and WCAG standards:
	* [http://www.section508.gov](http://www.section508.gov)
	* [http://www.w3.org/TR/WCAG20/](http://www.w3.org/TR/WCAG20/)

##### Indexability

We must use semantic markup that's readable and logical when JavaScript and CSS are off. All page content must be in HTML; we don't want to use iframes or JavaScript for loading initial indexable content.
All links should be to HTML destinations.

```html
<a href="/shelf/jordan/page/2" title="">
```

Instead of

```html
<a href="javascript:loadPage(2);" title="">
```

This lets the page get indexed correctly by search engines as well as allows users to open in new tabs and windows.
