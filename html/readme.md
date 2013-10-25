### HTML

			
All mark-up should be clean, optimised and valid, and should be formatted the same throughout all projects:

* The HTML mark-up should comply with UK web accessibility law and should follow the Web Content Accessibility Guidelines as closely as possible.
* Any web project will have the same basic directory structure, the boilerplate can be [downloaded here](https://github.com/zizther/Jam).
* Start any project using HTML5.
* When using HTML5, make sure you have an understanding of the tags. This will help with development and SEO (read the documentation!).
* Keep all images in the graphics directory, there is no need to place stylesheet images in the css directory.
* Lowercase should be used throughout.
* Underscore should be used for classes and unique identifiers; no dashes or camel-casing.
* Use classes and unique identifiers correctly. It is best practice to use OOCSS and use classes to manage this.
* Good SEO mark-up should be used, e.g. only one ```<h1>``` per page.
* Put style sheets at the top in ```<head></head>```
* Inline styles should <u><strong>only</strong></u> be used when necessary.

* Each main closing tag block should end with a comment, such as:

		```<!-- / #tag_name -->``` and ```<!-- / .tag_name -->```

* All HTML should be indented 1 tab (4 spaces).
* Use double quotation marks (" ") rather than single (' ') for attribute values where necessary.

* Place id's and class's before any other attribute on an element.

		```<input class="form_input" id="name" name="name" type="text" value="">```
		
* Try to keep HTTP request down to a minimum.
* Use [image sprites](http://www.w3schools.com/css/css_image_sprites.asp) where possible.
* Always optimise images for web. Optmise them using a program like Codekit or use something like [smushit.com](http://www.smushit.com) (provided by Yahoo!).
* In most cases, JS can be placed at the bottom before ```</body>```, unless it is absolutely required at the top.
* Google analytics should be placed before ```</head>```.
* Where possible, use other CDNs to deliver content, such as Google code to delivery jQuery.
* Make favicon small and cacheable.
* Minimize the number of iframes.
* Choose ```<link>``` over @import.
* Don't scale images in HTML unless they are responsive.
* Optimise images; some images can be exported smaller as a .png over a .jpg. Look to see what is best.
* Use .png over .gif
* Avoid empty image ```src=""``` tags.
* Conditional Comments can be used, but not because you’re lazy.
	
		```<!--[if IE]>  <![endif]-->```
	
* Place suitable title and alt tags on links and images. Do not leave them blank.
* Use favicons.
* Use suitable meta data in the ```<head>```. If the client has provided some, review and add tags if required. If not, use the default tags provided the boilerplate.
* Make sure to add the description tag. Don’t leave it empty (but don’t fill it with useless gunk either).
* Find out if Google and/or Bing verification meta keys are required.
