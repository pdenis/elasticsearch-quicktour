Query
======

Search query : 

```json
GET /wikipedia/_search
{
  "query": {
    "match": {
      "text": "bacterial"
    }
  }
}
```
Same with query string : GET /wikipedia/_search?q=text:bacterial

```json
GET /wikipedia/_search
{
  "query": {
    "match_phrase": {
      "text": "bacterial chromosome"
    }
  }
}
```

Filtered query

Filter by ID

```json
GET /wikipedia/_search
{
  "query": {
    "filtered": {
      "filter": {
        "term": {
          "_id": "1628"
        }
      }
    }
  }
}
```

Search for "bacterial" & filter by stub=false

```json
GET /wikipedia/_search
{
  "query": {
    "filtered": {
      "filter": {
        "term": {
          "stub": false
        }
      },
      "query": {
        "match": {
          "title": "bacterial"
        }
      }
    }
  }
}
```

Search for documents (10 < docs < 20) about history & astronomy with a boost for documents about meteor
Sorting by ID desc

```json
GET /wikipedia/_search
{
  "query": {
    "bool": {
      "must": {"match": {"text": "history"}},
      "should": {"match": {"title": "astronomy"}},
      "should": {"match": {"text": "meteor^2"}}
    }
  },
  "sort": [
    {
      "_id": {
        "order": "desc",
      },
    }
  ],
  "size": 10
  "from": 10
}
```