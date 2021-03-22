# Elasticsearch Percolate

The normal workflow elasticsearch is storing a JSON document using a index and exceute searches ask the index of those documents. Percolation is the oppposite of the normal workflow. Searches are stored and documents are used to ask the index of those searches. One of the application of elasticsearch percolate is to find the domain specific words in a document. The words are stored using the index and documents are passed as search query to get all the domain specific words in the given documents. 

## Create Index

To create an index -
```bash
curl -X PUT "localhost:9200/my-index-000001?pretty" -H 'Content-Type: application/json' -d'
{
  "mappings": {
    "properties": {
      "query": {
        "type": "percolator"
      },
      "field": {
        "type": "text"
      }
    }
  }
}
'
```
Here, 'my-index-000001' is the index name.

## Insert a single value into index

To insert the words that will be searched into the index -
```bash
curl -X PUT "localhost:9200/my-index-000001/_doc/match_value?pretty" -H 'Content-Type: application/json' -d'
{
  "query": {
    "match": {
      "field": "value"
    }
  }
}
'
```
Here, 'match_value' will be used as an index and 'value' is the word that should be tied to the index.

## Insert bulk entries into the index

To index multiple values at once -
```bash
curl -X PUT "localhost:9200/my-index-000001/_bulk?pretty" -H 'Content-Type: application/json' -d'
{"index":{"_index":"some_index","_type":".percolator","_id":"1"}}
{"query":{"match":{"whatever_field":"some value 1"}}}
{"index":{"_index":"some_index","_type":".percolator","_id":"2"}}
{"query":{"match":{"whatever_field":"some value 2"}}}
{"index":{"_index":"some_index","_type":".percolator","_id":"3"}}
{"query":{"match":{"whatever_field":"some value 3"}}}
'
```