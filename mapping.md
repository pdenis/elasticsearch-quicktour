Mapping
=======

Create a french wiki mapping with a type "page"

```json
POST /wiki
{
  "mappings": {
	 "page": {
	    "_all": {
	       "enabled": false
	    },
	    "_size": {
	       "enabled": true,
	       "store": true
	    },
	    "properties": {
	       "category": {
	          "type": "string",
	          "index": "not_analyzed"
	       },
	       "link": {
	          "type": "string"
	       },
	       "stub": {
	          "type": "boolean"
	       },
	       "text": {
	          "type": "string",
	          "analyzer": "french"
	       },
	       "title": {
	          "type": "string",
	          "analyzer": "french"
	       }
	    }
	 }
  },
  "settings": {
     "number_of_shards": 2,
     "number_of_replicas": 1
  }
}
```

GET /wiki/_mapping

Update mapping : 

```json
PUT /wiki
{
  "mappings": {
	 "page": { 
	    "_all": {
	       "enabled": false
	    },
	    "_size": {
	       "enabled": true,
	       "store": true
	    },
	    "properties": {
	       "category": {
	          "type": "string",
	          "index": "not_analyzed"
	       },
	       "link": {
	          "type": "string"
	       },
	       "stub": {
	          "type": "boolean"
	       },
	       "text": {
	          "type": "string",
	          "analyzer": "french"
	       },
	       "title": {
	          "type": "string"
	       }
	    }
	 }
  },
  "settings": {
     "number_of_shards": 2,
     "number_of_replicas": 1
  }
}
```