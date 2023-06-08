---
description: >-
  This page provides details about the nftGet GraphQL query, which is used to
  retrieve information about an NFT (Non-Fungible Token) from Offsetdata.
---

# nftGet

### `nftGet` Query

The query allows you to retrieve detailed information about an NFT based on its metadata. The `nftGet` query supports the following parameters:

**Parameters**

| Name                | Type   | Description                                                                    |
| ------------------- | ------ | ------------------------------------------------------------------------------ |
| `meta`              | Object | An object containing metadata for the NFT retrieval process.                   |
| `meta.apikey`       | String | The API key used for authentication.                                           |
| `meta.chain`        | String | The blockchain network on which the NFT is located (e.g., "eth" for Ethereum). |
| `meta.tokenAddress` | String | The address of the NFT contract to which the token belongs.                    |
| `meta.tokenId`      | String | The unique identifier of the NFT token to be retrieved.                        |

**Response**

The `nftGet` query returns an object with the following fields:

<table data-full-width="false"><thead><tr><th>Field</th><th>Type</th><th>Response </th></tr></thead><tbody><tr><td><code>status</code></td><td>String</td><td><br><mark style="color:green;"><code>Mapped</code></mark> (if the token does not exist and is being mapped to Offsetdata)<br><br><mark style="color:red;"><code>Token already exists</code></mark> (if the token already exists and mapping is not needed)<br><br><mark style="color:red;"><code>Failed to get token URI on eth</code></mark> (if the token does not exist on the provided chain, eg. Ethereum)<br><br><mark style="color:red;"><code>Chain not supported</code></mark> (if a non-supported chain is provided), "Invalid Key" (if an invalid API key is provided)</td></tr></tbody></table>

**Additional query fields**

The `nftGet` query returns an object with the following fields:

<table data-full-width="false"><thead><tr><th>Additional Fields</th><th>Type</th><th>Response </th></tr></thead><tbody><tr><td><code>chain</code></td><td>String</td><td>Name of the blockchain where token exists</td></tr><tr><td><code>tokenAddress</code></td><td>String</td><td>NFT Token Address</td></tr><tr><td></td><td></td><td></td></tr></tbody></table>

**Example Usage**

The following example demonstrates how to use the `nftGet` query to retrieve information about an NFT token:

```
graphql query {
  nftGet(meta: {
    apikey: "API_KEY"
    chain: "eth"
    tokenAddress: "0xb334a4eb0a2d6cc24fd451e779c002b9b33228c3"
    tokenId: "1"
  }) {
    status
  }
}

```

**Code Examples**

Here are some code examples of how the `nftGet` endpoint can be used in various cases:

{% tabs %}
{% tab title="curl" %}
```bash
curl -X POST \
  -H "Content-Type: application/json" \
  -d '{
    "query": "query { nftGet(meta: { apikey: \"API_KEY\", chain: \"eth\", tokenAddress: \"0xb334a4eb0a2d6cc24fd451e779c002b9b33228c3\", tokenId: \"1\" }) { status } }"
  }' \
  https://api.offsetdata.com/graphql
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
const fetch = require('node-fetch');
const query = `
  query {
    nftGet(meta: {
      apikey: "API_KEY",
      chain: "eth",
      tokenAddress: "0xb334a4eb0a2d6cc24fd451e779c002b9b33228c3",
      tokenId: "1"
    }) {
      status
    }
  }
`;

fetch("https://api.offsetdata.com/graphql", {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ query }),
})
  .then(response => response.json())
  .then(({ data }) => {
    const { status } = data.nftGet;
    console.log('Retrieval status:', status);
  })
  .catch(error => console.error('Error:', error));
```
{% endtab %}

{% tab title="Javascript Axios" %}
```javascript
import axios from 'axios';
const query = {
  query: `query {
    nftGet(meta: {
      apikey: "API_KEY",
      chain: "eth",
      tokenAddress: "0xb334a4eb0a2d6cc24fd451e779c002b9b33228c3",
      tokenId: "1"
    }) {
      status
    }
  }`
};

axios.post('https://api.offsetdata.com/graphql', query)
  .then(({ data }) => {
    const status = data.data.nftGet.status;
    console.log('Retrieval status:', status);
  })
  .catch(error => {
    console.error('Error:', error);
  });


```
{% endtab %}

{% tab title="Python" %}
```python
import requests
query = '''
  query {
    nftGet(meta: {
      apikey: "API_KEY",
      chain: "eth",
      tokenAddress: "0xb334a4eb0a2d6cc24fd451e779c002b9b33228c3",
      tokenId: "1"
    }) {
      status
    }
  }
'''

response = requests.post("https://api.offsetdata.com/graphql", json={'query': query}).json()
status = response['data']['nftGet']['status']
print('Retrieval status:', status)


```
{% endtab %}
{% endtabs %}

Please note that this document assumes the base URL for the API to be `https://api.offsetdata.com/graphql`. Adjust the base URL if necessary.

The response from the API will contain the status of the mapping process in the `data.nftGet.status` field.

Make sure to replace `"API_KEY"` with your actual API key to authenticate the request.

