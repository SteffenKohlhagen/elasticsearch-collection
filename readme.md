## ph / f - Problematik - Mapping Filter - char_filter

Index mit _put anlegen:
```javascript
{
    "settings": {
        "analysis": {
            "analyzer": {
                "mein_analyzer": {
                    "tokenizer": "keyword",
                    "char_filter": [
                        "mein_filter"
                    ]
                }
            },
            "char_filter": {
                "mein_filter": {
                    "type": "mapping",
                    "mappings": [
                        "ph => f",
                        "f => ph"
                    ]
                }
            }
        }
    }
}
```