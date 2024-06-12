# Tabulator.js FAQs

## responsive layout

* Q: How to make the combination of `layout: "fitColumns"` and `responsiveLayout: "collapse",` work?
* A: You need to set a `minWidth` to at least one column
* Example implentation: https://dig-ed-cat.acdh.oeaw.ac.at/editions.html [code](https://github.com/acdh-oeaw/dig-ed-cat-static/blob/main/html/js/editions.js)

* Q: Togle Column visiblity. I need some widget listing (initially) all hidden columns, something like https://datatables.net/examples/api/show_hide.html (but nicer)