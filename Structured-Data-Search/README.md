Structured Data Search
================================

*Data Definition and Format written in Cascade CMS v20230712 (8.23)*

**data-definition.xml**

* Copy/paste entire `<system-data-structure>` into XML view of a new, blank Data Definition.
* Supports up to 3 levels of nested data.

**structured-data-search.vm**

* Outputs JSON array wrapped in `<script>` tags.
* `.toJson()` will list everything in alphabetical order.
* Order does not matter for schema specification.

https://developers.google.com/search/docs/appearance/structured-data/intro-structured-data

Format: JSON-LD, https://json-ld.org/  
Vocab:  https://schema.org/docs/full.html  
Test:   https://validator.schema.org/

<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/80x15.png" /></a><br /><span xmlns:dct="http://purl.org/dc/terms/" href="http://purl.org/dc/dcmitype/Text" property="dct:title" rel="dct:type">Structured Data Search Format</span> by <a xmlns:cc="http://creativecommons.org/ns#" href="https://www.hannonhill.com/" property="cc:attributionName" rel="cc:attributionURL">Charlie Holder, Hannon Hill</a> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License</a>.