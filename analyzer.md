Analyzer
========

Define Analyzers, filters, tokenizers

```json
PUT /my_index
{
    "settings": {
        "analysis": {
            "char_filter": { ... custom character filters ... },
            "tokenizer":   { ...    custom tokenizers     ... },
            "filter":      { ...   custom token filters   ... },
            "analyzer": {​
				"my_analyzer": {​
					"type": "custom",​
					"char_filter": [ "html_strip", "my_char" ], ​
					"tokenizer": "standard", ​
					"filter": [ " lowercase", "my_stopwords" ]​
				} ​
			}
        }
    }
}
```
