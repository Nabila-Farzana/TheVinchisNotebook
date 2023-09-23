---
title: "AWS serverless search application"
date: 2020-09-15T11:30:03+00:00
toc : true
# weight: 1
# aliases: ["/first"]
tags: ["AWS"]
author: "Nabila Farzana"
# author: ["Me", "You"] # multiple authors
# showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
description: "How to build a search application with Amazon Opensearch Serverless, Dynamodb and AWS lambda in a serverless manner"
# canonicalURL: "https://canonical.url/to/page"
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: false
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true

editPost:
    URL: "https://github.com/Nabila-Farzana/ThevinchisNotebook/blob/main/content/"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---


## The backstory
I was involved in a project focused on developing a fleet management system. One of the core functionalities of this system was the ability to search for available trips through a public API. Initially, we implemented this search feature using DynamoDB's query operation. However, we encountered a significant limitation with this approach. DynamoDB's query operation has a strict constraint: it can retrieve a maximum of 1 MB of data, and this limit is enforced before the filter expression is applied. As our data volume increased, this limitation became problematic, as our system couldn't locate trips that fell outside of that 1 MB data limit. To address this challenge, our solution was to implement AWS Serverless OpenSearch.

In this post I will demonstrate how I built a simple web based seach application using the [ Amazon OpenSearch Serverless ](https://docs.aws.amazon.com/opensearch-service/latest/developerguide/serverless-overview.html).


## The diagram 
![The implementation diagram](images/opensearch_implementation.png)
