# Typesense FAQs

## default sort order

* Q: How to determine the default sort order (without any search executed)
* A: define a [default_sorting_field](https://typesense.org/docs/26.0/api/collections.html#schema-parameters) in your collection-schema; see e.g. [emt-static](https://github.com/emt-project/emt-static/blob/main/make_typesense_index.py#L134)
* A: client side set `sort_by: "rec_id:asc"` under `additionalSearchParameters` see e.g. [schnitzler-mikrofilme](https://github.com/arthur-schnitzler/schnitzler-mikrofilme-static/blob/ba956b6ba04cd85e54b12be3019f37c8c2b7e24c/html/js/search.js#L17)