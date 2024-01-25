---
description: >-
  This page provides a list of API Endpoints and a detailed description of each
  of them.
---

# Endpoints

## DATA Endpoints

### Data Add:

* [dataAdd](broken-reference/)

The dataAdd endpoint allows you to add data to a specified chain (Polygon, Binance Smart Chain, BASE Chain, Camino Network, Polygon ZkEvm). It is used for `Simple` or `Advanced` data records.

### Data Verify:

* [dataVerify](broken-reference/)

The dataVerify endpoint allows you to verify the integrity of data stored on a specified chain (Polygon, Binance Smart Chain, BASE Chain, Camino Network, Polygon ZkEvm). It is used for `Simple` or `Advanced` data records.

### Data Find:

* [dataFind](broken-reference/)

The dataFind endpoint allows you to find specific data stored on a chain using its hash value or submission hash. This endpoint is used for `Single` record stored on the blockchain.

### Data All:

* [dataAll](broken-reference/)

The dataAll endpoint allows you to retrieve all the data records stored on the chain that belongs to the submitter. Each record contains information such as the chain it belongs to, record and submission details.

## UTILITY Endpoints

### Price Get:

* [priceGet](broken-reference/)

The priceGet endpoint allows you to retrieve the current and most up-to-date price of the specific token from the price oracle.

### Transaction Get:

* [txGet](broken-reference/)

The txGet endpoint allows you to retrieve incoming and outgoing transaction details from a specific chain. You can retrieve ERC20 or ERC721 and native transactions.

### Revoke Api Key

* [userRevokeKey](broken-reference/)

The userRevokeKey endpoint allows you to revoke or deactivate your API key. This operation can not be reversed back.

### API Usage

* [userUsage](broken-reference/)

The userUsage endpoint allows you to retrieve usage statistics and cost information associated with API key.

### API Version

* [version](broken-reference/)

The version endpoint allows you to retrieve current version information and status of the API Service.
