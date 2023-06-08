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

| Field          | Type   | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| -------------- | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `status`       | String | <p>The status of the mapping process. Possible values:<br><br><mark style="color:green;"><code>Mapped</code></mark> (if the token does not exist and is being mapped to Offsetdata),<br><br><mark style="color:red;"><code>Token already exists</code></mark> (if the token already exists and mapping is not needed),<br><br><mark style="color:red;"><code>Failed to get token URI on eth</code></mark> (if the token does not exist on the provided chain, eg. Ethereum)<br><br><mark style="color:red;"><code>Chain not supported</code></mark> (if a non-supported chain is provided), "Invalid Key" (if an invalid API key is provided).</p> |
| `chain`        | String | The blockchain network on which the NFT is located.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| `tokenAddress` | String | The address of the NFT contract to which the token belongs.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `tokenId`      | String | The unique identifier of the NFT token.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| `name`         | String | The name of the NFT token.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| `description`  | String | The description of the NFT token.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `symbol`       | String | The symbol or ticker of the NFT token.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| `tokenType`    | String | The type of the NFT token.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| `tokenUri`     | Object | An object containing the URI of the NFT token. It includes both the raw URI and the gateway URI.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| `media`        | Object | An object containing media-related information of the NFT token, such as the raw media, gateway media, thumbnail, and format.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `attributes`   | Array  | An array of attribute objects, each containing the value and trait\_type of a specific attribute of the NFT token.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `layer1`       | Object | An object containing detailed information about the NFT token's layer1 properties, such as name, description, symbol, token URI, media, attributes, properties, audio, and virtual assets.                                                                                                                                                                                                                                                                                                                                                                                                                                                         |

Please note that some fields within the `layer1` object may be optional or specific to certain types of NFTs.

**Example Usage**

The following example demonstrates how to use the `nftGet` query to retrieve information about an NFT token:

```graphql
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
    tokenId
    name
    description
    symbol
    tokenType
    tokenUri {
      raw
      gateway
    }
    media {
      raw
      gateway
      thumbnail
      format
    }
    attributes {
      value
      trait_type
    }
    layer1 {
      name
      description
      symbol
      tokenUri {
        raw
        gateway
      }
      media {
        image_data
        background_image
        image_url
        background_color
        animation_url
        external_url
        youtube_url
        raw
        gateway
        thumbnail
        format
        mimeType
      }
      attributes {
        value
        trait_type
        display_type
        key
        max_value
        link
      }
      properties {
        points
        status
        type
        owner
        price
        ipfs
        location
        license
        edition
        date
        gender
        id
        is_normalized
        version
        last_request_date
      }
      audio {
        artist
        title
        duration
        losslessAudio
        bpm
        artwork
        credits
        lyrics
        genre
        isrc
        key
      }
      virtual {
        asset3d
        tpose
        model
        pfp
        experience
        interactivity
      }
    }
  }
}
```

**Code Examples**

Here are some code examples of how the `nftGet` endpoint can be used in various cases:

\{% tabs %\} \{% tab title="curl" %\}

```bash
curl -X POST \
  -H "Content-Type: application/json" \
  -d '{
    "query": "query { nftGet(meta: { apikey: \"API_KEY\", chain: \"eth\", tokenAddress: \"0xb334a4eb0a2d6cc24fd451e779c002b9b33228c3\", tokenId: \"1\" }) { status chain tokenAddress tokenId name description symbol tokenType tokenUri { raw gateway } media { raw gateway thumbnail format } attributes { value trait_type } layer1 { name description symbol tokenUri { raw gateway } media { image_data background_image image_url background_color animation_url external_url youtube_url raw gateway thumbnail format mimeType } attributes { value trait_type display_type key max_value link } properties { points status type owner price ipfs location license edition date gender id is_normalized version last_request_date } audio { artist title duration losslessAudio bpm artwork credits lyrics genre isrc key } virtual { asset3d tpose model pfp experience interactivity } } }"
  }' \
  https://api.offsetdata.com/graphql
```

\{% endtab %\}

\{% tab title="Node.js" %\}

```bash
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
      chain
      tokenAddress
      tokenId
      name
      description
      symbol
      tokenType
      tokenUri {
        raw
        gateway
      }
      media {
        raw
        gateway
        thumbnail
        format
      }
      attributes {
        value
        trait_type
      }
      layer1 {
        name
        description
        symbol
        tokenUri {
          raw
          gateway
        }
        media {
          image_data
          background_image
          image_url
          background_color
          animation_url
          external_url
          youtube_url
          raw
          gateway
          thumbnail
          format
          mimeType
        }
        attributes {
          value
          trait_type
          display_type
          key
          max_value
          link
        }
        properties {
          points
          status
          type
          owner
          price
          ipfs
          location
          license
          edition
          date
          gender
          id
          is_normalized
          version
          last_request_date
        }
        audio {
          artist
          title
          duration
          losslessAudio
          bpm
          artwork
          credits
          lyrics
          genre
          isrc
          key
        }
        virtual {
          asset3d
          tpose
          model
          pfp
          experience
          interactivity
        }
      }
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
    const { status, chain, tokenAddress, tokenId, name, description, symbol, tokenType, tokenUri, media, attributes, layer1 } = data.nftGet;
    console.log('NFT status:', status);
  })
  .catch(error => console.error('Error:', error));

```

\{% endtab %\}

\{% tab title="Javascript Axios" %\}

```bash
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
      chain
      tokenAddress
      tokenId
      name
      description
      symbol
      tokenType
      tokenUri {
        raw
        gateway
      }
      media {
        raw
        gateway
        thumbnail
        format
      }
      attributes {
        value
        trait_type
      }
      layer1 {
        name
        description
        symbol
        tokenUri {
          raw
          gateway
        }
        media {
          image_data
          background_image
          image_url
          background_color
          animation_url
          external_url
          youtube_url
          raw
          gateway
          thumbnail
          format
          mimeType
        }
        attributes {
          value
          trait_type
          display_type
          key
          max_value
          link
        }
        properties {
          points
          status
          type
          owner
          price
          ipfs
          location
          license
          edition
          date
          gender
          id
          is_normalized
          version
          last_request_date
        }
        audio {
          artist
          title
          duration
          losslessAudio
          bpm
          artwork
          credits
          lyrics
          genre
          isrc
          key
        }
        virtual {
          asset3d
          tpose
          model
          pfp
          experience
          interactivity
        }
      }
    }
  }`,
};

axios.post('https://api.offsetdata.com/graphql', query)
  .then(({ data }) => {
    const { status, chain, tokenAddress, tokenId, name, description, symbol, tokenType, tokenUri, media, attributes, layer1 } = data.data.nftGet;
    console.log('NFT status:', status);
  })
  .catch(error => console.error('Error:', error));

```

\{% endtab %\} \{% endtabs %\}

Please note that this document assumes the base URL for the API to be `https://api.offsetdata.com/graphql`. Adjust the base URL if necessary.

The response from the API will contain the status of the mapping process in the `data.nftMap.status` field.

Make sure to replace `"API_KEY"` with your actual API key to authenticate the request.

\
