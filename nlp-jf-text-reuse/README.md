# NLP-Jour-Fix 
2026-04-02

## Trying to build, deploy and maybe scale a text reuse detection tool with Postgres, Python and Django

### The project/corpus
* The Roman conquest of Jerusalem in 70 AD: Reception, use, and interpretation in the Middle Ages (c.600-c.1200)
* Text passages from hetergoenous texts (Chronical texts, sermons, commentaries (bibl), ...); see https://jerusalem-70-ad.github.io/jad-astro/dashboard/
* ~ 2500 passages, different length (min 4 words, max 91.000 words), Average Words Per Passage: 439
* latin texts

### The question
* who copies whom?

### The solution
* create sentence embeddings and calculate proximity
* via a Django/Django-Rest-Framework API [https://jad-graph-db.acdh-dev.oeaw.ac.at/](https://jad-graph-db.acdh-dev.oeaw.ac.at/)
* Provide some gui interface [https://jerusalem-70-ad.github.io/jad-astro/ai-graph/](https://jerusalem-70-ad.github.io/jad-astro/ai-graph/?jadId=1&amount=3&collection=JAD+sentences&maxDistance=0.1)

### the implementation
#### preprocess the texts
* clean the text with [ai assisted genereated regex](https://github.com/acdh-oeaw/jad-graph-db/blob/main/archiv/utils.py#L8)
* handle [abbreviations](https://github.com/acdh-oeaw/jad-graph-db/blob/main/archiv/utils.py#L36)
* sentence splitting; something like split after every `. ` with some exceptions

#### data model
* two tables: Collection and Text Snippet; see [https://jad-graph-db.acdh-dev.oeaw.ac.at/data-model](https://jad-graph-db.acdh-dev.oeaw.ac.at/data-model)
* no good solution yet how to store several embeddings, currently new field/row for each model/vector-size

#### embeddings
* first attempt -> use https://platform.openai.com/ and text-embedding-3-small
* we must not use those things any more!
* local model: nomic-embed-text-v1.5, lm-studio > ollama > llama.ccp but all via OpenAi API
* via django-mgm command: https://github.com/acdh-oeaw/jad-graph-db/blob/main/jad/management/commands/update_jad.py

### Facit
* basically easy to do, BUT
* text-processing
* using local models brings quite some deployment overhead
* evaluation (I don't know latin) and embedding model selection
  * processing and storing different embeddings