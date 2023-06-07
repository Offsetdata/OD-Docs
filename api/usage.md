---
description: >-
  This page provides a high-level overview of how to use the Offsetdata API and
  highlights its key features.
---

# Usage

## Offsetdata API Usage Documentation

The Offsetdata API is a powerful tool that allows you to interact with the Offsetdata platform and access its various features programmatically. The API is built using [GraphQL](https://graphql.org), a flexible query language for APIs and is compatible with all major programming languages.\
\
You can learn more about Graphql from the [official documentation](https://graphql.org/learn/).

### API Endpoint

The Offsetdata API endpoint is located at [https://api.offsetdata.com/graphql](https://api.offsetdata.com/graphql). This is the base URL that you will use to make API requests and interact with the Offsetdata platform.

### Query Example

To retrieve information about the current version of the Offsetdata API, you can use the following GraphQL query:

```javascript
query {
  version {
    current
    date
    creator
    company
    status
  }
}
```

This query allows you to fetch details such as the current API version, the date of the version, the creator, the company, and the status of the API.

Please note that this is a basic example to demonstrate the query structure. In practice, there are many more endpoints and query options available in the Offsetdata API, which will be explained in detail in their respective documentation.\
\


### Encoded Query Parameter

You can encode query parameters to test API endpoints in the browser with the help of [GraphiQL ](https://github.com/graphql/graphiql/tree/main/packages/graphiql)tool.

{% embed url="https://api.offsetdata.com/graphql?query=query%20%7B%0A%20%20version%20%7B%0A%20%20%20%20current%0A%20%20%20%20date%0A%20%20%20%20creator%0A%20%20%20%20company%0A%20%20%20%20status%0A%20%20%7D%0A%7D" %}
Encoded Query
{% endembed %}

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption><p>GraphiQL Browser Tool</p></figcaption></figure>

### GraphQL Flexibility

GraphQL provides a flexible and efficient way to retrieve data from the Offsetdata API. With GraphQL, you have control over the data you request and can avoid over-fetching or under-fetching of information. You can tailor your queries to only request the specific data you need, which can improve performance and reduce unnecessary data transfer.

### Detailed Documentation

For comprehensive and detailed information on each endpoint and the available query options, please refer to the Offsetdata API documentation. The API documentation provides in-depth explanations, query examples, and guidelines on how to interact with the various endpoints and utilize the full potential of the Offsetdata API.

### In-Short

The Offsetdata API offers a wide range of capabilities for integrating Offsetdata's features into your applications. By utilizing GraphQL, you have the flexibility to query the API and retrieve specific data tailored to your needs. Make sure to refer to the detailed documentation for a complete understanding of the available endpoints and their functionalities.

If you have any questions or encounter any issues while using the Offsetdata API, please refer to the documentation or reach out to the Offsetdata support team for further assistance.
