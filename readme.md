
# Sammlung von Elasticsearch calls
 



## ph / f - Problematik - Mapping Filter - char_filter
http://xxxxxxxxxxxxx/elasticsearch/meinindex
Einen Index mit _put anlegen:
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

Dann kann z.B über einen Analyser ausgewertet werden:
http://xxxxxxxxxxxxx/elasticsearch/meinindex/_analyze
```javascript
{
  "analyzer": "mein_analyzer",
  "text": "Geografie ist die Wissenschaft von der Erde und ihrem Aufbau. Aber Geographie steht auch im Wiki...",
  "explain" : true
}
```