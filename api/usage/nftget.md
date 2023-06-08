---
description: >-
  This page provides details about the nftGet GraphQL query, which is used to
  retrieve information about an NFT (Non-Fungible Token) from Offsetdata.
---

# nftGet

### `nftGet` Query

The query allows you to retrieve detailed information about an NFT based on its metadata. The `nftGet` query supports the following parameters:

**Parameters**

| Name                | Type   | Description                                                                |
| ------------------- | ------ | -------------------------------------------------------------------------- |
| `meta`              | Object | An object containing metadata for the NFT retrieval process.               |
| `meta.apikey`       | String | API key used for authentication.                                           |
| `meta.chain`        | String | Blockchain network on which the NFT is located (e.g., "eth" for Ethereum). |
| `meta.tokenAddress` | String | Address of the NFT contract to which the token belongs.                    |
| `meta.tokenId`      | String | Unique identifier of the NFT token to be retrieved.                        |

**Response**

The `nftGet` query returns an object with the following fields:

<table data-full-width="false"><thead><tr><th>Field</th><th>Type</th><th>Response</th></tr></thead><tbody><tr><td><code>status</code></td><td>String</td><td><br><mark style="color:green;"><code>Mapped</code></mark> (if the token does not exist and is being mapped to Offsetdata)<br><br><mark style="color:red;"><code>Token already exists</code></mark> (if the token already exists and mapping is not needed)<br><br><mark style="color:red;"><code>Failed to get token URI on eth</code></mark> (if the token does not exist on the provided chain, eg. Ethereum)<br><br><mark style="color:red;"><code>Chain not supported</code></mark> (if a non-supported chain is provided), "Invalid Key" (if an invalid API key is provided)</td></tr></tbody></table>

**Additional query fields**

The `nftGet` query returns an object with the following fields:

<table><thead><tr><th width="264">Additional Fields</th><th width="97.33333333333331">Type</th><th>Response</th></tr></thead><tbody><tr><td><code>chain</code></td><td>String</td><td>Blockchain network on which the NFT is located.</td></tr><tr><td><code>tokenAddress</code></td><td>String</td><td>Address of the NFT contract from which the token is retrieved.</td></tr><tr><td><code>tokenId</code></td><td>String</td><td>Unique identifier of the NFT token.</td></tr><tr><td><code>name</code></td><td>String</td><td>Name of the NFT token.</td></tr><tr><td><code>description</code></td><td>String</td><td>Description of the NFT token.</td></tr><tr><td><code>symbol</code></td><td>String</td><td>Symbol of the NFT token.</td></tr><tr><td><code>tokenType</code></td><td>String</td><td>Type of the NFT token, e.g ERC721, ERC1155</td></tr><tr><td><strong><code>tokenUri</code></strong></td><td><strong>Object</strong></td><td><code>tokenUri {</code> <a data-footnote-ref href="#user-content-fn-1"><code>...</code></a> <code>}</code></td></tr><tr><td>          <code>raw</code></td><td>String</td><td>Raw token URI of the NFT.</td></tr><tr><td>          <code>gateway</code></td><td>String</td><td>Gateway token URI of the NFT.</td></tr><tr><td><strong><code>media</code></strong></td><td><strong>Object</strong></td><td><code>media {</code> <a data-footnote-ref href="#user-content-fn-2"><code>...</code></a> <code>}</code></td></tr><tr><td>          <code>raw</code></td><td>String</td><td>Raw media data of the NFT.</td></tr><tr><td>          <code>gateway</code></td><td>String</td><td>Gateway media data of the NFT.</td></tr><tr><td>          <code>thumbnail</code></td><td>String</td><td>Thumbnail image URL of the NFT media.</td></tr><tr><td>          <code>format</code></td><td>String</td><td>Format of the NFT media.</td></tr><tr><td><strong><code>attributes</code></strong></td><td><strong>Object</strong></td><td><code>attributes {</code> <a data-footnote-ref href="#user-content-fn-3"><code>...</code></a> <code>}</code></td></tr><tr><td>          <code>value</code></td><td>String</td><td>Value of the media attribute.</td></tr><tr><td>          <code>trait_type</code></td><td>String</td><td>Trait type of the media attribute.</td></tr><tr><td><mark style="color:blue;background-color:blue;"><strong><code>layer1</code></strong></mark></td><td><mark style="color:blue;"><strong>Object</strong></mark></td><td><mark style="color:blue;"><code>layer1 {</code></mark> <a data-footnote-ref href="#user-content-fn-4"><mark style="color:blue;"><code>...</code></mark></a> <mark style="color:blue;"><code>}</code></mark></td></tr><tr><td>          <code>name</code></td><td>String</td><td>Name of the NFT token on Layer 1.</td></tr><tr><td>          <code>description</code></td><td>String</td><td>Description of the NFT token on Layer 1.</td></tr><tr><td>          <code>symbol</code></td><td>String</td><td>Symbol of the NFT token on Layer 1.</td></tr><tr><td><strong><code>tokenUri</code></strong></td><td><strong>Object</strong></td><td><code>layer1 {tokenUri {</code> <a data-footnote-ref href="#user-content-fn-5"><code>...</code></a> <code>}}</code></td></tr><tr><td>          <code>raw</code></td><td>String</td><td>Raw token URI of the NFT.</td></tr><tr><td>          <code>gateway</code></td><td>String</td><td>Gateway token URI of the NFT.</td></tr><tr><td><strong><code>media</code></strong></td><td><strong>Object</strong></td><td><code>layer1 {media {</code> <a data-footnote-ref href="#user-content-fn-6"><code>...</code> </a><code>}}</code></td></tr><tr><td>          <code>image_data</code></td><td>String</td><td>Image data of the NFT.</td></tr><tr><td>          <code>background_image</code></td><td>String</td><td>Background image URL of the NFT.</td></tr><tr><td>          <code>image_url</code></td><td>String</td><td>Image URL of the NFT.</td></tr><tr><td>          <code>background_color</code></td><td>String</td><td>Background color of the NFT.</td></tr><tr><td>          <code>animation_url</code></td><td>String</td><td>Animation URL of the NFT media.</td></tr><tr><td>          <code>external_url</code></td><td>String</td><td>External URL of the NFT media.</td></tr><tr><td>          <code>youtube_url</code></td><td>String</td><td>YouTube URL of the NFT media.</td></tr><tr><td>          <code>raw</code></td><td>String</td><td>Raw media data of the NFT.</td></tr><tr><td>          <code>gateway</code></td><td>String</td><td>Gateway media data of the NFT.</td></tr><tr><td>          <code>thumbnail</code></td><td>String</td><td>Thumbnail image URL.</td></tr><tr><td>          <code>format</code></td><td>String</td><td>Format type of NFT media.</td></tr><tr><td>          <code>mimeType</code></td><td>String</td><td>MIME type of NFT media.</td></tr><tr><td><strong><code>attributes</code></strong></td><td><strong>Object</strong></td><td><code>layer1 {attributes {</code> <a data-footnote-ref href="#user-content-fn-7"><code>...</code></a> <code>}}</code></td></tr><tr><td>          <code>value</code></td><td>String</td><td>Value attribute.</td></tr><tr><td>          <code>trait_type</code></td><td>String</td><td>Trait type attribute.</td></tr><tr><td>          <code>display_type</code></td><td>String</td><td>Display type attribute.</td></tr><tr><td>          <code>key</code></td><td>String</td><td>Key value.</td></tr><tr><td>          <code>max_value</code></td><td>String</td><td>Maximum value associated with NFT.</td></tr><tr><td>          <code>link</code></td><td>String</td><td>External Link or URL</td></tr><tr><td><strong><code>properties</code></strong></td><td><strong>Object</strong></td><td><code>layer1 {properties {</code> <a data-footnote-ref href="#user-content-fn-8"><code>...</code></a> <code>}}</code></td></tr><tr><td>          <code>points</code></td><td>String</td><td>Number of points associated with the NFT token.</td></tr><tr><td>          <code>status</code></td><td>String</td><td>Status of the NFT token.</td></tr><tr><td>          <code>type</code></td><td>String</td><td>Type of the NFT token.</td></tr><tr><td>          <code>owner</code></td><td>String</td><td>Current owner of the NFT token.</td></tr><tr><td>          <code>price</code></td><td>String</td><td>Price of the NFT token.</td></tr><tr><td>          <code>ipfs</code></td><td>String</td><td>IPFS (InterPlanetary File System) URL.</td></tr><tr><td>          <code>location</code></td><td>String</td><td>Location information of the NFT token.</td></tr><tr><td>          <code>license</code></td><td>String</td><td>License information associated with the NFT token.</td></tr><tr><td>          <code>edition</code></td><td>String</td><td>Edition information of the NFT token.</td></tr><tr><td>          <code>date</code></td><td>String</td><td>Date associated with the NFT token.</td></tr><tr><td>          <code>gender</code></td><td>String</td><td>Gender information associated with the NFT token.</td></tr><tr><td>          <code>id</code></td><td>String</td><td>Unique identifier of the NFT token.</td></tr><tr><td>          <code>is_normalized</code></td><td>String</td><td>Indicates whether the NFT token is normalized.</td></tr><tr><td>          <code>version</code></td><td>String</td><td>Version information associated with the NFT token</td></tr><tr><td>         <code>last_request_date</code></td><td>String</td><td>Date of the last request made for the NFT token.</td></tr><tr><td><strong><code>audio</code></strong></td><td><strong>Object</strong></td><td><code>layer1 {audio {</code> <a data-footnote-ref href="#user-content-fn-9"><code>...</code></a> <code>}}</code></td></tr><tr><td>         <code>artist</code></td><td>String</td><td>Artist or creator of the audio associated with the NFT token.</td></tr><tr><td>         <code>title</code></td><td>String</td><td>Audio title or name of the audio associated with the NFT token.</td></tr><tr><td>         <code>duration</code></td><td>String</td><td>Duration of the audio in seconds.</td></tr><tr><td>         <code>losslessAudio</code></td><td>String</td><td>Indicates whether the audio is in a lossless format.</td></tr><tr><td>         <code>bpm</code></td><td>String</td><td>Beats per minute (BPM) of the audio.</td></tr><tr><td>         <code>artwork</code></td><td>String</td><td>Artwork associated with the audio.</td></tr><tr><td>         <code>credits</code></td><td>String</td><td>Credits information for the audio.</td></tr><tr><td>         <code>lyrics</code></td><td>String</td><td>Lyrics of the audio.</td></tr><tr><td>         <code>genre</code></td><td>String</td><td>Genre of the audio.</td></tr><tr><td>         <code>isrc</code></td><td>String</td><td>International Standard Recording Code (ISRC) associated with the audio.</td></tr><tr><td>         <code>key</code></td><td>String</td><td>Key information of the audio.</td></tr><tr><td><strong><code>virtual</code></strong></td><td><strong>Object</strong></td><td><code>layer1 {virtual {</code> <a data-footnote-ref href="#user-content-fn-10"><code>...</code></a> <code>}}</code></td></tr><tr><td>         <code>asset3d</code></td><td>String</td><td>3D asset associated with the virtual representation of the NFT token.</td></tr><tr><td>         <code>tpose</code></td><td>String</td><td>T-pose information of the virtual representation.</td></tr><tr><td>         <code>model</code></td><td>String</td><td>3D model information of the virtual representation.</td></tr><tr><td>         <code>pfp</code></td><td>String</td><td>Profile picture (PFP) information of the virtual representation.</td></tr><tr><td>         <code>experience</code></td><td>String</td><td>Experience information associated with the virtual representation.</td></tr><tr><td>         <code>interactivity</code></td><td>String</td><td>Interactivity features available in the virtual representation.</td></tr></tbody></table>

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

[^1]: `raw, gateway`

[^2]: `raw, gateway, thumbnail, format`

[^3]: `value, trait_type`

[^4]: `name description symbol tokenUri { raw gateway } media { image_data background_image image_url background_color animation_url external_url youtube_url raw gateway thumbnail format mimeType }` \
    `attributes { value trait_type display_type key max_value link } properties { points status type owner price ipfs location license edition date gender id is_normalized version last_request_date } audio { artist title duration losslessAudio bpm artwork credits lyrics genre isrc key } virtual { asset3d tpose model pfp experience interactivity }`

[^5]: `raw, gateway`

[^6]: `image_data, background_image, image_url, background_color, animation_url, external_url, youtube_url, raw, gateway, thumbnail, format, mimeType`

[^7]: 

    ```
    value, trait_type, display_type, key, max_value, link
    ```

[^8]: `points, status, type, owner, price, ipfs, location, license, edition, date, gender, id, is_normalized, version, last_request_date`

[^9]: `artist, title, duration, losslessAudio, bpm, artwork, credits, lyrics, genre, isrc, key`

[^10]: `asset3d, tpose, model, pfp, experience, interactivity`
