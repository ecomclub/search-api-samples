# Samples of items search

## Pages
1. [Samples of items search](./)

## Summary
1. [Introduction](#introduction)
2. [Search body examples](#search-body-examples)
    * [Search by brands](#search-by-brands)
    * [Search by brands and categories](#search-by-brand-and-categories)

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

## Search by brands
```json
{
  "query": {
    "bool": {
      "filter": [
        {
          "terms": {
            "brands.name": [ "BRAND_NAME" ]
          }
        }
      ]
    }
  }
}
```

## Search by brands and categories
```json
{
  "query": {
    "bool": {
      "filter": [
        {
          "terms": {
            "brands.name": [ "BRAND1", "BRAND2", "BRAND3" ]
          }
        },
        {
          "terms": {
            "categories.name": [ "CATEGORY_NAME" ]
          }
        }
      ]
    }
  }
}
```

{% endraw %}
