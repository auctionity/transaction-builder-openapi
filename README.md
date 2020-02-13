# [Auctionity Saleroom](https://app.auctionity.com/) - TransactionBuilder API (v1.0.0-alpha)


## The API endpoint
```
https://tx.auctionity.com/
```

## [JSON OpenAPI Spec](openapi.json)
## [YAML OpenAPI Spec](openapi.yml)

## Build a transaction to create an auction
### API Endpoint : POST `/transaction/auction/create`

```
{
  "from": "0xFf5001f5C780D02C9433B926bc457Ef2979fd588",
  "auction": {
    "auctionId": "0x41451874774DBdC0ac42262b44D5B5d1285fe6D7",
    "currency": {
      "contractAddress": "0x6c099b6664ADD0732Ca57DE47eCE17a024c20410",
      "id": "0x00",
      "amount": "0x01"
    },
    "timeBegin": "0x5E4510B3",
    "timeEnd": "0x5E4510B8",
    "sponsor": "0x6c099b6664ADD0732Ca57DE47eCE17a024c20410",
    "antiSnippingTrigger": "0x1e",
    "antiSnippingDuration": "0x1e",
    "reward": {
      "master": "0x1e",
      "auctionSponsor": "0x32",
      "bidAuctioneer": "0x1e", 
      "bidSponsor": "0xa",
      "lastBidSponsor": "0xa",
    },
    "bidIncrement": "0x01",
    "tokens": [
      {
        "contractAddress": "0x06012c8cf97BEaD5deAe237070F9587f8E7A266d",
        "id": "0x230d",
        "amount": "0x01"
      }
    ]
  }
}
```

## Build a transaction to bid on auction
### API Endpoint : POST `/transaction/auction/{auctionId}/bid`

```
{
  "from": "0xFf5001f5C780D02C9433B926bc457Ef2979fd588",
  "bid": {
    "amount": "0x01",
    "sponsor": "0x2F42E25fdF28D92D172913F9e24744e7Ded72408",
    "auctioneer": "0xb0667271e2f6E471BCE5c3A7636e066aB6760b8f"
  }
}
```

## Build a ERC20/ERC721/ERC1155 deposit transaction 
### API Endpoint : POST `/transaction/auction/{auctionId}/end`
```
{
  "from": "0xD572F4d1828a3fb31ec0202437b0b6A25DCfa9D0",
  "token": {
    "contractAddress": "0x06012c8cf97bead5deae237070f9587f8e7a266d",
    "id": "0x4d2",
    "amount": "0x01"
  }
}
```

## Build a ERC20/ERC721/ERC1155 withdraw transaction
### API Endpoint : POST `/transaction/auction/{auctionId}/end`
```
{
  "from": "0xD572F4d1828a3fb31ec0202437b0b6A25DCfa9D0",
  "token": {
    "contractAddress": "0x06012c8cf97bead5deae237070f9587f8e7a266d",
    "id": "0x4d2",
    "amount": "0x01"
  }
}
```

## Build a transaction to generate reclaim voucher at the end of an auction
### API Endpoint : PUT `/transaction/auction/{auctionId}/end`

## Build a transaction to receive your gain
### API Endpoint : POST `/transaction/auction/{auctionId}/end`
```
{
  "voucher": "0x12bc14bf00000000000000000000000000000000000000000000000000000000000000003ffef300598c53c390cc06992a95eeda792198eca1e81ae7a25c1752b4d67a03000000000000000000000000000000000000000000000000000000000000008000000000000000000000000000000000000000000000000000000000000000e00000000000000000000000000000000000000000000000000000000000000034248586cd626bc7291fb1b6b4d9411c07eed1f89d000000000000000000000000000000000000000000000000000000000000000a0000000000000000000000000000000000000000000000000000000000000000000000000000000000000041149f323d86c5ad23fc54b2cdbf4e5486cbfb3be1ebc1ec562b42a855549897181799515d49a47073222c6774c2a669fa80596986388c0a0c2d90655963dcbf8d1b00000000000000000000000000000000000000000000000000000000000000"
}
```