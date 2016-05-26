####References

https://www.elastic.co/guide/en/elasticsearch/reference/current/analysis-ngram-tokenizer.html


```rb
curl -XPUT 'localhost:9200/test' -d '
{
  "settings": {
    "analysis": {
      "analyzer": {
        "my_ngram_analyzer": {
          "tokenizer": "my_ngram_tokenizer"
        }
      },
      "tokenizer": {
        "my_ngram_tokenizer": {
          "type": "nGram",
          "min_gram": "2",
          "max_gram": "3",
          "token_chars": ["letter", "digit"]
        }
      }
    }
  }
}'
```
```rb
curl 'localhost:9200/test/_analyze?pretty=1&analyzer=my_ngram_analyzer' -d 'FC Schalke 04'
```

```rb
curl 'localhost:9200/flubber_test_5b168215-2f91-49dc-8607-3d0ecf0b97ff/_analyze?pretty=1&analyzer=index_ngram_analyzer' -d 'Brown foxes'
```
