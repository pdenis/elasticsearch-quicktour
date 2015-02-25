Aggregations
============

Get category terms count (10 first) & links count by category (10 first)

```json
GET /wikipedia/_search
{
  "aggs": {
    "category_count": {
      "terms": {
        "field": "category",
        "size": 10
    
      },
      "aggs": {
        "link_count": {
          "terms": {
            "field": "link",
            "size": 10
          }
        }
      }
    }
  }
}
```