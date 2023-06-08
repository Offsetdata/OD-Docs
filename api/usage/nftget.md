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

<table data-full-width="false"><thead><tr><th>Field</th><th>Type</th><th>Response</th></tr></thead><tbody><tr><td><code>status</code></td><td>String</td><td><br><mark style="color:green;"><code>Mapped</code></mark> (if the token does not exist and is being mapped to Offsetdata)<br><br><mark style="color:red;"><code>Token already exists</code></mark> (if the token already exists and mapping is not needed)<br><br><mark style="color:red;"><code>Failed to get token URI on eth</code></mark> (if the token does not exist on the provided chain, eg. Ethereum)<br><br><mark style="color:red;"><code>Chain not supported</code></mark> (if a non-supported chain is provided), "Invalid Key" (if an invalid API key is provided)</td></tr></tbody></table>

**Additional query fields**

The `nftGet` query returns an object with the following fields:

<table><thead><tr><th>Additional Fields</th><th width="254.33333333333331">Type</th><th>Response</th></tr></thead><tbody><tr><td><code>chain</code></td><td>String</td><td>The blockchain network on which the NFT is located.</td></tr><tr><td><code>tokenAddress</code></td><td>String</td><td>The address of the NFT contract from which the token is retrieved.</td></tr><tr><td><code>tokenId</code></td><td>String</td><td>The unique identifier of the NFT token.</td></tr><tr><td><code>name</code></td><td>String</td><td>The name of the NFT token.</td></tr><tr><td><code>description</code></td><td>String</td><td>The description of the NFT token.</td></tr><tr><td><code>symbol</code></td><td>String</td><td>The symbol of the NFT token.</td></tr><tr><td><code>tokenType</code></td><td>String</td><td>The type of the NFT token, e.g ERC721, ERC1155</td></tr><tr><td><strong><code>tokenUri</code></strong></td><td>Object</td><td><code>tokenUri {raw, gateway}</code></td></tr><tr><td>          <code>raw</code></td><td>String</td><td>The raw token URI of the NFT.</td></tr><tr><td>          <code>gateway</code></td><td>String</td><td>The gateway token URI of the NFT.</td></tr><tr><td><strong><code>media</code></strong></td><td>Object</td><td><code>media {raw, gateway, thumbnail, format}</code></td></tr><tr><td>          <code>raw</code></td><td>String</td><td>The raw media data of the NFT.</td></tr><tr><td>          <code>gateway</code></td><td>String</td><td>The gateway media data of the NFT.</td></tr><tr><td>          <code>thumbnail</code></td><td>String</td><td>The thumbnail image URL of the NFT media.</td></tr><tr><td>          <code>format</code></td><td>String</td><td>The format of the NFT media.</td></tr><tr><td><strong><code>attributes</code></strong></td><td>Object</td><td><code>attributes {value, trait_type}</code></td></tr><tr><td>          <code>value</code></td><td>String</td><td>The value of the media attribute.</td></tr><tr><td>          <code>trait_type</code></td><td>String</td><td>The trait type of the media attribute.</td></tr><tr><td><mark style="color:green;"><strong><code>layer1</code></strong></mark></td><td><mark style="color:green;">Object</mark></td><td><mark style="color:green;"><code>layer1 { ... }</code></mark></td></tr><tr><td>          <code>name</code></td><td>String</td><td>The name of the NFT token on Layer 1.</td></tr><tr><td>          <code>description</code></td><td>String</td><td>The description of the NFT token on Layer 1.</td></tr><tr><td>          <code>symbol</code></td><td>String</td><td>The symbol of the NFT token on Layer 1.</td></tr><tr><td><mark style="color:blue;"><strong><code>tokenUri</code></strong></mark></td><td><mark style="color:blue;">Object</mark></td><td><mark style="color:blue;"><code>layer1 {</code></mark><br>  <mark style="color:blue;"><code>tokenUri {raw, gateway}</code></mark><br><mark style="color:blue;"><code>}</code></mark></td></tr><tr><td>          <code>raw</code></td><td>String</td><td>The raw token URI of the NFT on Layer 1.</td></tr><tr><td>          <code>gateway</code></td><td>String</td><td>The gateway token URI of the NFT on Layer 1.</td></tr><tr><td><strong><code>media</code></strong></td><td>Object</td><td><code>layer1 {</code><br>  <code>media {</code> <a data-footnote-ref href="#user-content-fn-1"><code>...</code> </a><code>}</code><br><code>}</code></td></tr><tr><td><code>layer1.media.image_data</code></td><td>String</td><td>The image data of the NFT media on Layer 1.</td></tr><tr><td><code>layer1.media.background_image</code></td><td>String</td><td>The background image URL of the NFT media on Layer 1.</td></tr><tr><td><code>layer1.media.image_url</code></td><td>String</td><td>The image URL of the NFT media on Layer 1.</td></tr><tr><td><code>layer1.media.background_color</code></td><td>String</td><td>The background color of the NFT media on Layer 1.</td></tr><tr><td><code>layer1.media.animation_url</code></td><td>String</td><td>The animation URL of the NFT media on Layer 1.</td></tr><tr><td><code>layer1.media.external_url</code></td><td>String</td><td>The external URL of the NFT media on Layer 1.</td></tr><tr><td><code>layer1.media.youtube_url</code></td><td>String</td><td>The YouTube URL of the NFT media on Layer 1.</td></tr><tr><td><code>layer1.media.raw</code></td><td>String</td><td>The raw media data of the NFT on Layer 1.</td></tr><tr><td><code>layer1.media.gateway</code></td><td>String</td><td>The gateway media data of the NFT on Layer 1.</td></tr><tr><td><code>layer1.media.thumbnail</code></td><td>String</td><td>The thumbnail image URL of the NFT media on Layer 1.</td></tr><tr><td><code>layer1.media.format</code></td><td>String</td><td>The format of the NFT media on Layer 1.</td></tr><tr><td><code>layer1.media.mimeType</code></td><td>String</td><td>The MIME type of the NFT media on Layer 1.</td></tr><tr><td><code>layer1.attributes</code></td><td>Array</td><td>An array of attribute objects related to Layer 1.</td></tr><tr><td><code>layer1.attributes.value</code></td><td>String</td><td>The value of the Layer 1 attribute.</td></tr><tr><td><code>layer1.attributes.trait_type</code></td><td>String</td><td>The trait type of the Layer 1 attribute.</td></tr><tr><td><code>layer1.attributes.display_type</code></td><td>String</td><td>The display type of the Layer 1 attribute.</td></tr><tr><td><code>layer1.attributes.key</code></td><td>String</td><td>The key of the Layer 1 attribute.</td></tr><tr><td><code>layer1.attributes.max_value</code></td><td>String</td><td>The maximum value of the Layer 1 attribute.</td></tr><tr><td><code>layer1.attributes.link</code></td><td>String</td><td>The link of the Layer 1 attribute.</td></tr><tr><td><code>layer1.properties</code></td><td>Object</td><td>The properties of the NFT token on Layer 1.</td></tr><tr><td><code>layer1.audio</code></td><td>Object</td><td>The audio information of the NFT token on Layer 1.</td></tr><tr><td><code>layer1.virtual</code></td><td>Object</td><td>The virtual asset information of the NFT token on Layer 1.</td></tr></tbody></table>

***

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
    chain
    tokenAddress
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

[^1]: `image_data, background_image, image_url, background_color, animation_url, external_url, youtube_url, raw, gateway, thumbnail, format, mimeType`
