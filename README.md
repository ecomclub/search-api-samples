# Samples of items search

## Pages
1. [Samples of items search](https://ecomclub.github.io/search-api-samples/)

## Summary
1. [Introduction](#introduction)
2. [Search body examples](#search-body-examples)
    * [Search by brands](#serch-by-brands)
    * [Search by brands and categories](#serch-by-brand-and-categories)

{% raw %}

# Introduction
This document is intended to provide examples of
<a href="https://www.elastic.co/guide/en/elasticsearch/reference/current/search-request-body.html" target="_blank">
Request Body Search</a> (Elasticsearch), for faster and flexible products searches within
<a href="https://ecomsearch.docs.apiary.io/" target="_blank">
E-Com Plus Search API</a>.

You should use the examples below as request body of
<a href="https://ecomsearch.docs.apiary.io/#reference/items/items-search/complex-search" target="_blank">
Items Complex Search</a> reference.

## Search by brand
```json
{
  "query": {
    "bool": {
      "filter": [
        {
          "term": {
            "visible": true
          }
        },
        {
          "terms": {
            "brands.name": [ "BRAND_NAME" ]
          }
        }
      ]
    }
  },
  "sort": [
    {
      "available": {
        "order": "desc"
      }
    },
    "_score",
    {
      "ad_relevance": {
        "order": "desc"
      }
    },
    {
      "views": {
        "order": "desc"
      }
    }
  ]
}
```

```json
{
  "query": {
    "bool": {
      "filter": [
        {
          "term": {
            "visible": true
          }
        },
        {
          "terms": {
            "brands.name": [ "BRAND1", "BRAND2" ]
          }
        }
      ]
    }
  },
  "sort": [
    {
      "available": {
        "order": "desc"
      }
    },
    "_score",
    {
      "ad_relevance": {
        "order": "desc"
      }
    },
    {
      "views": {
        "order": "desc"
      }
    }
  ]
}
```

```json
{
  "query": {
    "bool": {
      "filter": [
        {
          "term": {
            "visible": true
          }
        },
        {
          "term": {
            "brands.id": "BRAND_ID"
          }
        }
      ]
    }
  },
  "sort": [
    {
      "available": {
        "order": "desc"
      }
    },
    "_score",
    {
      "ad_relevance": {
        "order": "desc"
      }
    },
    {
      "views": {
        "order": "desc"
      }
    }
  ]
}
```

{% endraw %}
