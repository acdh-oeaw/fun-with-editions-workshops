# Tabulator.js FAQs

## responsive layout

* Q: How to make the combination of `layout: "fitColumns"` and `responsiveLayout: "collapse",` work?
* A: You need to set a `minWidth` to at least one column
* Example implentation: https://dig-ed-cat.acdh.oeaw.ac.at/editions.html [code](https://github.com/acdh-oeaw/dig-ed-cat-static/blob/main/html/js/editions.js)

## toggle column visiblity

* Q: Toggle Column visiblity. I need some widget listing (initially) all hidden columns, something like https://datatables.net/examples/api/show_hide.html (but nicer)
* A: See [Tabulator documentation](https://tabulator.info/examples/6.2#menu) (this shows all columns, not just the hidden ones)
* Example implementation: https://grocerist.github.io/grocerist-app/documents.html [code](https://github.com/grocerist/grocerist-app/blob/e2728b15afa8c806b5475bb901d4f2a43e4731b8/html/js/documents.js#L6)
* Update: in case of responsive tables, the table needs to be redrawn after the toggle visibility line (i.e. add `table.redraw();` ) to make use of the available space and potentially uncollapse any columns that were collapsed before

## background color

* Q: How do I change the background color of the table? Is there an easy/easier way than e.g. https://github.com/emt-project/emt-static/blob/main/html/css/tablutor-style.css
* A: One way to solve the problem would be to change the standard tabulator CSS if you provide it together with the other page data (without CDN). Make sure to name the files in a way that makes it clear they have been modified.

## How to configure default sorting
* Q: How to configure default sorting
* A: Add  `initialSort: [{ column: "columnToSortBy", dir: "desc" }]` to the Tabulator config. You can add several columns to sort by, here's an example from the documentation:
```
 var table = new Tabulator("#example-table", {
    initialSort:[
        {column:"age", dir:"asc"}, //sort by this first
        {column:"height", dir:"desc"}, //then sort by this second
    ]
});
```
This would lead to a list that starts with the tallest person and for persons with the same height, they will be sorted by their age. (i.e. the "first" and "second" from the documentation can be a bit misleading)
Also, the default sorting is string, so if your column contains another datatype, you need to add define an appropriate sorter for the column (=add to the column config), e.g. `sorter: "number"` for numbers. There are different [built-in sorters](https://tabulator.info/docs/6.2/sort#func-builtin) or you can define a custom sorting function.
