# Migrate from Tabulator to DataTables

## why?

* Tabulator.js had a better API than DataTables v1.x
* This changed with DataTables v2.x. DataTables is also larger (more people develop and use it).
* DataTables provides more features (responsiveness, data formatting, a11y, searching, filtering) out of the box

## migration

see <https://github.com/karl-kraus/kb-static/blob/main/xslt/listbibl.xsl> / <https://karl-kraus.github.io/kb-static/listbibl.html> for an example

<https://karl-kraus.github.io/kb-static/listbibl.html>

* copy & paste [js/datatables_custom](https://github.com/karl-kraus/kb-static/tree/main/html/js/datatables_custom) folder
* copy & paste [vendor/datatables](https://github.com/karl-kraus/kb-static/tree/main/html/vendor/datatables) folder
* remove all tabulator-js code (in vendor, in xsl-partials and in html/js)
* in xsl files with table:
  * import `<xsl:import href="./partials/datatables_import.xsl"/>`
  * add `<xsl:call-template name="datatables_import"/>` to header
  * add `<script src="js/datatables_custom/datatables_custom.js"></script>` before `</body>`

### custom attributes

* `<th scope="col" data-dt-visible="false">ID</th>`  -> col is not visible by default
* `<th scope="col" data-dt-searchlist="true" >Kategorie</th>` -> if data-dt-searchlist="true" the values of the column are presented as filter drop down list

I think that's basically it (but I'm sure I forgot something ...)
