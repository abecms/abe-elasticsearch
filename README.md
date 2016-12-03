# abe-elasticsearch
Add search feature on your Abe frontend with Elasticsearch

##Introduction
This plugin will index all you published content to Elasticsearch so that you can add a search feature to your static frontend !

## Pre-requisites
Elasticsearch installed.

## Configuration
Configure the Elasticsearch parameters in your abe.json file.

```
"elasticsearch":{
  "active":"true",
  "host": "127.0.0.1",
  "port": "9200",
  "index": "my_index"
 }
```

you can deactivate this plugin by setting "active" to false
If you don't provide an "index" value, the plugin will take the name of your project directory

## How it works

### On your Abe CMS
Every time you publish a content, abe-elasticsearch will publish the whole document to Elasticsearch.
Every time you unpublish a content, abe-elasticsearch will delete this content from Elasticsearch.

### On your client
Note: If you want to request Elasticsearch directly from the client, configure your config/elasticsearch.yml configuration file with:

```
http.cors.enabled : true
 
http.cors.allow-origin : "*"
http.cors.allow-methods : OPTIONS, HEAD, GET, POST, PUT, DELETE
http.cors.allow-headers : X-Requested-With,X-Auth-Token,Content-Type, Content-Length

```

You'll find a specific recipe on this plugin here: https://github.com/gregorybesson/recipe-elasticsearch
