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

Example: [`/items/0xcf98266882dba141c1ad748a71634e65e308e803/11`](https://api.wraptag.io/items/0xcf98266882dba141c1ad748a71634e65e308e803/11)

**Data return examples**

```json
{
  "address":"0xcf98266882dba141c1ad748a71634e65e308e803",
  "id":"11",
  "owner":"0xdf12af9598cf39b7ab486551b94b88f31282ab7d",
  "trueOwner":"0xdf12af9598cf39b7ab486551b94b88f31282ab7d",
  "album": [
    "QmcuvQKQVTMWFwce3tjxGMCLRHfYVf8ehuEQ1gnkcKsF2x?filename=138C619B-0A1A-48E7-8C84-33DE764179DB.jpeg",
    "QmNyi87jNqp12sBuvoxtsWriyqbABc5yAmTJExzdgk4Chu?filename=93954C2F-EC87-4CCB-BE94-91E0F95987B4.jpeg",
    "QmeRuWSaswk9eFrtyCNwqXzgtedodwpB12T5PfZCcqGGvR?filename=D0DB7766-A9AB-4B4C-9494-C392A6197FA5.jpeg",
    "QmUoRnpw9c4ENWVzm535EoY4uVNmuTEhZcVHg6WzqCWRRr?filename=20DCABD9-FC98-4192-AAD5-DF463EA4F1B6.jpeg",
    "Qmegbuoy8c4qXRrR9wU2dMiJsjJ8QESDG9oma69zyxKUs5?filename=62EA9856-BF12-4286-8EDF-DDA7BC1DA65F.png",
    "QmUyYDK4QspDH3GJxcmfMvNV1QTZ35xqUyL3rfjSnJLzhd?filename=1153503B-A2F9-493E-9525-4F792DB8C4AD.webp",
    "QmY4RDzWy183HW5BcPSeL6qxSZxcQikUSqq5TB9ATdX1jr?filename=0FB85B9E-D713-4060-8646-0F97210372B8.png",
    "QmY6VgkzVsq2ByoJZmoLQp2aHw9mLW62nS3bx1gdCc9opR?filename=7C9C4081-5EF0-4FC2-997A-9B541A1D8324.png",
    "QmWLF4dvLZ3abh2jLV6wyuuofruxz8UxpkBFJ5Q1utsfo9?filename=611DBFA9-A9C0-49E3-8066-2E85ACD1571E.png",
    "QmQVjusgDCzVnDAaGvPHeNM9HunYvic7vMkrTGecquN4Ro?filename=662E29F0-6FAD-40F7-BE52-806D765F23A5.png",
    "QmYKBduLBEamsKegucp8R6rgwC9EobhwQp8S4bBwLuk6Px?filename=E07B2828-FBF3-4DD8-834B-3A9396D29D15.png"
  ],
  "attributes": [
    {"trait_type":"Category","value":"iphone 12 promax"},
    {"trait_type":"Product name","value":"iphone"},
    {"trait_type":"Color","value":"xanh"},
    {"trait_type":"Size","value":"lớn"},
    {"trait_type":"Buyer","value":"loan"},
    {"trait_type":"Purchase date","value":"2021-12-10"},
    {"trait_type":"Price","value":"1000$"},{"trait_type":"Purchase place","value":"viet nam"},
    {"trait_type":"Manufacturer","value":"mỹ"},
    {"trait_type":"Production Date","value":"2021-12-25"},
    {"trait_type":"Serial Number","value":"146789"},
    {"trait_type":"Manufacturing Location","value":"mỹ"},
    {"trait_type":"Tag creator","value":"0x149954e14141e18524b3b30333c3c394d831719c"},
    {"trait_type":"WrapTag ID","value":"04993B09700000"},
    {"trait_type":"Memo","value":"Lorem Ipsum is simply dummy text of the printing and typesetting industry..."}
  ],
  "dataHash":"Qmf2Ayhyf6Fa9Fr7Ca5C5hATNNr4PCUgQNWo1TLztBF7gK?filename=NFT-Details.json",
  "hash":"0x440dbb9c5d7c9075ec3b0e8075db984665f013cef49df5769d282dabc08f4c47",
  "name":"iphone",
  "nftimage":"QmNyi87jNqp12sBuvoxtsWriyqbABc5yAmTJExzdgk4Chu?filename=46232614-A243-48CE-91AA-A1FFF0784D7B.jpeg",
  "pdf":"QmaNxbQNrJdLzzd8CKRutBjMZ6GXRjvuPepLuNSsfdeJRJ?filename=sample.pdf",
  "status":"active",
  "tagId":"04993B09700000",
  "timestamp":1638327305020,
  "totalLike":2,
  "uniqueKey":"0xcf98266882dba141c1ad748a71634e65e308e803_11",
  "video":"QmVFmzAznqKM4KuWLe3jKPqWBAS7Y2FKq8j4EgWZYFeoCw?filename=trim.683658AA-D5DD-43FD-9569-7EFB8771ECA8.MOV",
  "creator": {
    "image":"QmWg9HBV5mSQibgk3qMpBLhR7t4nHZ8n1YAaDXpn5KUtZH?filename=20211014_112801.jpg",
    "username":"我的4标签",
    "address":"0x149954e14141e18524b3b30333c3c394d831719c"
  },
  "histories":[
    {
      "image":"QmSpLq4ieGdrY41f2Fhabi4aKfs7zzJkMJqDUcuM34BvsN?filename=Hinh-nen-dien-thoai-cu-te-2.jpeg",
      "username":"0xdf12...ab7d",
      "address":"0xdf12af9598cf39b7ab486551b94b88f31282ab7d"
    },
    {
      "image":"QmWg9HBV5mSQibgk3qMpBLhR7t4nHZ8n1YAaDXpn5KUtZH?filename=20211014_112801.jpg",
      "username":"我的4标签",
      "address":"0x149954e14141e18524b3b30333c3c394d831719c"
    },
    {
      "image":"QmWg9HBV5mSQibgk3qMpBLhR7t4nHZ8n1YAaDXpn5KUtZH?filename=20211014_112801.jpg",
      "username":"我的4标签",
      "address":"0x149954e14141e18524b3b30333c3c394d831719c"
    },
    {
      "image":"QmWg9HBV5mSQibgk3qMpBLhR7t4nHZ8n1YAaDXpn5KUtZH?filename=20211014_112801.jpg",
      "username":"我的4标签",
      "address":"0x149954e14141e18524b3b30333c3c394d831719c"
    },
    { 
      "image":"QmWg9HBV5mSQibgk3qMpBLhR7t4nHZ8n1YAaDXpn5KUtZH?filename=20211014_112801.jpg",
      "username":"我的4标签",
      "address":"0x149954e14141e18524b3b30333c3c394d831719c"
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
