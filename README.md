# Public API Documentation
[General Info](#General_Info)  
[Get List User](#Get_List_User)  
[Get User Info](#Get_User_Info)  
[Get List Item](#Get_List_Item)  
[Get Item Info](#Get_Item_Info)  


# General_Info
#### API Domain: https://api.wraptag.io
#### IPFS Domain: https://ipfsgw.wraptag.io/ipfs
  - Example: [https://ipfsgw.wraptag.io/ipfs/QmcuvQKQVTMWFwce3tjxGMCLRHfYVf8ehuEQ1gnkcKsF2x](https://ipfsgw.wraptag.io/ipfs/QmcuvQKQVTMWFwce3tjxGMCLRHfYVf8ehuEQ1gnkcKsF2x)  

#### Tag NFT: [0xcf98266882dba141c1ad748a71634e65e308e803](https://tomoscan.io/address/0xcf98266882dba141c1ad748a71634e65e308e803)
#### Wraptag POINT (TRC21): [0x7d11e5eacde7e89c06ce73cf39ebbd65eead031d](https://tomoscan.io/address/0x7d11e5eacde7e89c06ce73cf39ebbd65eead031d)

# Get_List_User

Get list user

**URL** : `/users`

**Method** : `GET`

## Success Response

**Code** : `200 OK`

**Available Query**
  * limit: item per page
  * page: page number
  * key: search by username
  
Example: [`/users?limit=5&page=1&key=rose`](https://api.wraptag.io/users?limit=5&page=1&key=rose)

**Data return examples**

```json
{
  "data": [
    {
      "address": "0xc0574b51147c7d8aff8dce16da0e3b49a026f895",
      "username": "Rose",
      "image": "QmQs2ft5CoKP8dFC2Xm1pEWopAELT3ciWBiUE4BnCuVjub",
      "totalItem": 0
    }
  ],
  "page": 1,
  "limit": 5,
  "total": 1,
  "pages": 1
}
```

# Get_User_Info

Get user info

**URL** : `/users/{userAddress}`

**Method** : `GET`

## Success Response

**Code** : `200 OK`

Example: [`/users/0xc0574b51147c7d8aff8dce16da0e3b49a026f895`](https://api.wraptag.io/users/0xc0574b51147c7d8aff8dce16da0e3b49a026f895)

**Data return examples**

```json
{
  "address": "0xc0574b51147c7d8aff8dce16da0e3b49a026f895",
  "image":"QmQs2ft5CoKP8dFC2Xm1pEWopAELT3ciWBiUE4BnCuVjub",
  "introduction":"A Wraptag User",
  "profileImage":"QmexaSxgfj8do2TQdDK4B93aAReZuhMndCQRnitFhkNiVF",
  "totalLike":0,
  "username":"Rose"
}
```

When userAddress does not exist.

```json
{
  "statusCode": 404,
  "message": "User not found"
}
```

# Get_List_Item

Get list item

**URL** : `/items`

**Method** : `GET`

## Success Response

**Code** : `200 OK`

**Available Query**

  * limit: item per page
  * page: page number
  * key: search by item name
  * userAddress: get item of specific user
  
Example: [`/items?limit=5&page=1&userAddress=0xdf12af9598cf39b7ab486551b94b88f31282ab7d`](https://api.wraptag.io/items?limit=5&page=1&userAddress=0xdf12af9598cf39b7ab486551b94b88f31282ab7d)

**Data return examples**

```json
{
  "data": [
    {
      "address": "0xcf98266882dba141c1ad748a71634e65e308e803",
      "id": "11",
      "name": "iphone",
      "nftimage": "QmNyi87jNqp12sBuvoxtsWriyqbABc5yAmTJExzdgk4Chu?filename=46232614-A243-48CE-91AA-A1FFF0784D7B.jpeg",
      "totalLike": 2
    }
  ],
  "page": 1,
  "limit": 5,
  "total": 1,
  "pages": 1
}
```

# Get_Item_Info

Get Item Info

**URL** : `/items/{itemAddress}/{itemId}`

**Method** : `GET`

## Success Response

**Code** : `200 OK`

Example: [`/items/0xcf98266882dba141c1ad748a71634e65e308e803/45`](https://api.wraptag.io/items/0xcf98266882dba141c1ad748a71634e65e308e803/45)

**Data return examples**

```json
{
  "address": "0xcf98266882dba141c1ad748a71634e65e308e803",
  "id": "45",
  "owner": "0xfe0feee01583ebd1be2d1572ae84879fa11e1b24",
  "trueOwner": "0xfe0feee01583ebd1be2d1572ae84879fa11e1b24",
  "album": [
    "QmR34dfMU9FK28KJbEpqgyyziHnzxJPGstULL1AUKtPpf4",
    "QmZddhfwDvS2mkiCC4wVek1ECV4TCHXTcUpkz2xUfRYrQe",
    "QmPCnFHtAYC9sY7QKGsVH9vcC3WCpZUcWZ6AmjHU6bvn7J",
    "QmeSodX6s5NhtTzEuYgmuiyGE2QiivVBnk2YxutddwPqTV"
  ],
  "attributes": [
    {
      "trait_type": "Category",
      "value": "Men's Shoes"
    },
    {
      "trait_type": "Product name",
      "value": "Adidas"
    },
    {
      "trait_type": "Color",
      "value": "FTWR WHITE/CORE BLACK/SOLAR YELLOW,NON-DYED/CORE BLACK/NIGHT FLASH,Carbon / Carbon / Solar Red,Cloud White / Core Black / Solar Red,Violet Tone / Violet Tone / Purple Tint"
    },
    {
      "trait_type": "Size",
      "value": "6UK"
    },
    {
      "trait_type": "Buyer",
      "value": "YURIKO"
    },
    {
      "trait_type": "Purchase date",
      "value": "07/12/2021"
    },
    {
      "trait_type": "Price",
      "value": "$217.21"
    },
    {
      "trait_type": "Purchase place",
      "value": "Supersports Vietnam"
    },
    {
      "trait_type": "Manufacturer",
      "value": "Adidas"
    },
    {
      "trait_type": "Producttion Date",
      "value": ""
    },
    {
      "trait_type": "Serial Number",
      "value": "FY0377,GZ9212,FY0838,FY3952,S23869"
    },
    {
      "trait_type": "Manufacturing Location",
      "value": ""
    },
    {
      "trait_type": "Tag creator",
      "value": "0xFE0FEEe01583eBd1bE2D1572ae84879Fa11e1b24"
    },
    {
      "trait_type": "WrapTag ID",
      "value": "53995A0D100043"
    },
    {
      "trait_type": "Memo",
      "value": "ULTRABOOST 21 SHOES.ENERGY WAS JUST ENERGY UNTIL ENERGY MET ULTRABOOST 21.Prototype after prototype. Innovation after innovation. Testing after testing. Meet us in the hot pursuit of the pinnacle harmonization of weight, cushioning, and responsiveness. Ultraboost 21. Say hello to incredible energy return."
    }
  ],
  "dataHash": "QmWJQqj1YbQRGD9tCCxhLRbR6uXLU8EPdjXMcHg5gHChAM",
  "hash": "0xd7aaef3b9fbe3b674d6335ca0d92403f321c362fdb11289872fa301621367d42",
  "name": "Adidas Ultraboost 21",
  "nftimage": "QmcAeri3QZyf6PzzY8P4G83U6o6J3usjpuGh3ZatSaBu7g",
  "pdf": "QmcjXkmEkfbiYrA4Yd4xeXAC4szGRqpRzoPLqX6gWU1NKD",
  "status": "active",
  "tagId": "53995A0D100043",
  "timestamp": 1638848703162,
  "totalLike": 0,
  "uniqueKey": "0xcf98266882dba141c1ad748a71634e65e308e803_45",
  "video": "QmdoKyQt6k7kHNY4Y6D1R3ToyG7DVKjG3ttxLCDE1ZtHxR",
  "creator": {
    "image": "Qmc1zBP63Uudcjx54djwwvxuvrDac1a8P6pb8Pjsj6aJ2R?filename=z2996200694794_e110cc120bae41e3d928e9ca9bd369b7.jpg",
    "username": "YURIKO",
    "address": "0xfe0feee01583ebd1be2d1572ae84879fa11e1b24"
  },
  "histories": [
    {
      "image": "Qmc1zBP63Uudcjx54djwwvxuvrDac1a8P6pb8Pjsj6aJ2R?filename=z2996200694794_e110cc120bae41e3d928e9ca9bd369b7.jpg",
      "username": "YURIKO",
      "address": "0xfe0feee01583ebd1be2d1572ae84879fa11e1b24"
    }
  ]
}
```

When item does not exist

```json
{
  "statusCode": 404,
  "message": "Item not found"
}
```
