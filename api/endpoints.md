---
description: >-
  This page provides a list of API Endpoints and a detailed description of each
  of them.
---

# Endpoints

## NFT Endpoints

### NFT Mapping:

* [nftMap](usage/nftmap.md)

The nftMap endpoint allows you to map an NFT token to Offsetdata. This mapping associates metadata and other relevant information with the NFT token, providing a way to access and retrieve data related to the token.

### NFT Get:

* [nftGet](usage/nftget.md)

The nftGet endpoint allows you to retrieve the metadata and associated information of a NFT token from Offsetdata. It includes details such as the status of the request, chain information, token address, token ID, name, description, symbol, token type, token URI, media details (including raw data, gateway, thumbnail, and format), attributes, layer1 information (including name, description, symbol, token URI, media details, attributes, properties, audio details, and virtual asset information).

### NFT Add:

* [nftAdd](broken-reference)

The nftAdd endpoint allows you to add a new NFT metadata object with various properties including name, image, description, attributes, properties, audio, and virtual assets.

### NFT Delete:

* [nftDel](broken-reference)

The nftDel endpoint allows you to delete a specific NFT metadata record from a given blockchain based on the token address and token ID provided.

### NFT Update:

* [nftUpd](broken-reference)

The nftUpd endpoint allows you to update the metadata and information of a specific NFT on a given blockchain. You can modify various attributes such as the token name, image, description, symbol, attributes, token URI, media details, properties, audio information, and virtual asset details.

### NFT Modify:

* [nftMod](broken-reference)

The nftMod endpoint allows you to modify modify the metadata and information of a specific NFT. You can modify attributes on layer 1 such as the token's title, description, symbol, token type, token URI, media details, attributes, properties, and virtual asset details.

### NFT Search:

* [nftSearch](broken-reference)

The nftSearch endpoint allows you to search for NFTs based on specific attributes, metadata properties and search parameters.

### NFT Map All:

* [nftMapAll](broken-reference)

The nftMapAll endpoint allows you to map whole collection, specific range of nfts or number of nfts within collection.

## DATA Endpoints

### Data Add:

* [dataAdd](broken-reference)

The dataAdd endpoint allows you to add data to a specified chain (Polygon, Binance Smart Chain, BASE Chain, Polygon ZkEvm). It is used for `Simple` or `Advanced` data records.

### Data Verify:

* [dataVerify](broken-reference)

The dataVerify endpoint allows you to verify verify the integrity of data stored on a specified chain (Polygon, Binance Smart Chain, BASE Chain, Polygon ZkEvm). It is used for `Simple` or `Advanced` data records.

### Data Find:

* [dataFind](broken-reference)

The dataFind endpoint allows you to u to find specific data stored on a chain using its hash value or submission hash. This endpoint is used for `Single` record stored on the blockchain.

### Data All:

* [dataAll](broken-reference)

The dataAll endpoint allows you to retrieve all the data records stored on the chain that belongs to submitter. Each record contains information such as the chain it belongs to, record and submission details.

## UTILITY Endpoints

### Price Get:

* [priceGet](broken-reference)

The priceGet endpoint allows you to retrieve the current and most up-to-date price of the specific token from the price oracle.

### Transaction Get:

* [txGet](broken-reference)

The txGet endpoint allows you to retrieve incoming and outgoing transaction details from a specific chain. You can retrieve ERC20 or ERC721 and native transactions.

### Revoke Api Key

* [userRevokeKey](broken-reference)

The userRevokeKey endpoint allows you to revoke or deactivate your API key. This operation can not be reversed back.

### API Usage

* [userUsage](broken-reference)

The userUsage endpoint allows you to retrieve usage statistics and cost information associated with API key.

### API Version

* [version](broken-reference)

The version endpoint allows you to retrieve current version information and status of API Service.
