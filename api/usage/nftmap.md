---
description: >-
  This page provides details about the nftMap GraphQL mutation, which is used to
  map NFTs (Non-Fungible Tokens) to Offsetdata.
---

# nftMap

### `nftMap` Mutation

The mutation allows you to specify the necessary parameters and returns the status of the mapping process. The `nftMap` mutation supports the following parameters:

#### Parameters

| Name                | Type   | Description                                                                    |
| ------------------- | ------ | ------------------------------------------------------------------------------ |
| `meta`              | Object | An object containing metadata for the NFT mapping process.                     |
| `meta.apikey`       | String | The API key used for authentication.                                           |
| `meta.chain`        | String | The blockchain network on which the NFT is located (e.g., "eth" for Ethereum). |
| `meta.tokenAddress` | String | The address of the NFT contract to which the token belongs.                    |
| `meta.tokenId`      | String | The unique identifier of the NFT token to be mapped.                           |

#### Response

The `nftMap` mutation returns an object with the following fields:

| Field    | Type   | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| -------- | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `status` | String | <p>The status of the mapping process. Possible values:<br><br><mark style="color:green;"><code>Mapped</code></mark> (if the token does not exist and is being mapped to Offsetdata),<br><br><mark style="color:red;"><code>Token already exists</code></mark> (if the token already exists and mapping is not needed),<br><br><mark style="color:red;"><code>Failed to get token URI on eth</code></mark> (if the token does not exist on the provided chain, eg. Ethereum)<br><br><mark style="color:red;"><code>Chain not supported</code></mark> (if a non-supported chain is provided), "Invalid Key" (if an invalid API key is provided).</p> |

#### Example Usage

The following example demonstrates how to use the `nftMap` mutation to map an NFT token to Offsetdata:

```graphql
graphql mutation {
  nftMap(meta: {
    apikey: "od-0000000000000000000000000000000000000000000"
    chain: "eth"
    tokenAddress: "0xb334a4eb0a2d6cc24fd451e779c002b9b33228c3"
    tokenId: "3650"
  }) {
    status
  }
}
```

#### cURL Example

Here's an example cURL command to perform the `nftMap` mutation:



{% tabs %}

{% tab title="curl" %}
```bash
curl -X POST \
  -H "Content-Type: application/json" \
  -d '{
    "query": "mutation { nftMap(meta: { apikey: \"od-0000000000000000000000000000000000000000000\", chain: \"eth\", tokenAddress: \"0xb334a4eb0a2d6cc24fd451e779c002b9b33228c3\", tokenId: \"3650\" }) { status } }"
  }' \
  https://api.offsetdata.com/graphql
```
{% endtab %}

{% tab title="Node.js" %}
```bash
const fetch = require('node-fetch');

const apiUrl = 'https://api.offsetdata.com/graphql';
const apiKey = 'od-0000000000000000000000000000000000000000000';
const chain = 'eth';
const tokenAddress = '0xb334a4eb0a2d6cc24fd451e779c002b9b33228c3';
const tokenId = '3650';

const query = `
  mutation {
    nftMap(meta: {
      apikey: "${apiKey}",
      chain: "${chain}",
      tokenAddress: "${tokenAddress}",
      tokenId: "${tokenId}"
    }) {
      status
    }
  }
`;

fetch(apiUrl, {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ query }),
})
  .then(response => response.json())
  .then(({ data }) => {
    const { status } = data.nftMap;
    console.log('Mapping status:', status);
  })
  .catch(error => console.error('Error:', error));

```
{% endtab %}

{% tab title="Javascript Axios" %}
```bash
curl -X POST \
  -H "Content-Type: application/json" \
  -d '{
    "query": "mutation { nftMap(meta: { apikey: \"od-0000000000000000000000000000000000000000000\", chain: \"eth\", tokenAddress: \"0xb334a4eb0a2d6cc24fd451e779c002b9b33228c3\", tokenId: \"3650\" }) { status } }"
  }' \
  https://api.offsetdata.com/graphql
```
{% endtab %}

{% endtabs %}

Please note that this document assumes the base URL for the API to be `https://api.offsetdata.com/graphql`. Adjust the base URL if necessary.

The response from the API will contain the status of the mapping process in the `data.nftMap.status` field.

Feel free to reach out if you have any further questions!
