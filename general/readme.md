## HTML

### General
This guide outlines best practices and guidelines for Maido. It is important that all developers follow this guide to keep consistency throughout all projects.

Any freelance or external developer will need to read this document and speak to a senior member of the digital team before he or she can start development. All work will be checked throughout the project by a member of the Maido digital team. All new projects should follow the boilerplate Maido uses, this can be [downloaded here](https://github.com/zizther/Jam).
			
A good guide to follow is the [YUI best practice](http://developer.yahoo.com/performance/rules.html).
		
#### Website aims
When developing a website, keep these points in mind:

* Use the guidelines provided in this document
* Develop the site to the design(s) provided
* Make it as pixel perfect as possible
* It must have a good user experience
* It must be easy to navigate
* Think about user perception
* Cross browser developed to IE8 (IE7 if required)
* Make sure your editor uses UTF-8 as character encoding, without a byte order mark
* Be consistent
			
If you’re editing code, take a few minutes to look at the code around you and determine its style.

The point of having style guidelines is to have a common vocabulary of coding so people can concentrate on what you’re saying rather than on how you’re saying it. We present global style rules here so people know the vocabulary, but local style is also important. If code you add to a file looks drastically different from the existing code around it, it throws readers out of their rhythm when they go to read it. Avoid this. 

**Avoid user CSS "hacks" — try a different approach first.**

It’s tempting to address styling differences over user agent detection or special CSS filters, workarounds, and hacks. This should be considered a last resort in order to achieve and maintain an efficient and manageable code base. Put another way, giving detection and hacks a free pass will hurt projects in the long run as projects tend to take the way of least resistance. That is, allowing and making it easy to use detection and hacks means using detection and hacks more frequently—and more frequently is too frequently. 

#### Think of the end user
We don’t want to create excessive sites with heavy images, wasted CSS and JS. In all areas, the code has to be clean and optimised, and any assets need to be optimised for web.
			
#### Other technologies
Depending on the project and what it is built with, other server side technology, such as database caching and template caching, can be used. Do not depend on this, though, as these will be used to further improve the user experience.