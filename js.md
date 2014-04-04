# JavaScript

---


### jQuery call in templates

If you are developing a site for IE9+ you can use jQuery 2.x. You can always provide a fallback to jQuert 1.x if you need to support IE8 by using the example below


``html
<!--[if (!IE)|(gt IE 8)]><!-->
  <script src="jquery-2.x.js"></script>
<!--<![endif]-->

<!--[if lte IE 8]>
  <script src="jquery-1.x.js"></script>
<![endif]-->
```