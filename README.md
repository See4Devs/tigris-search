# tigris-search
Sample on how to use tigris for real time search. With Tigris you don't need to add extra implementation like Elasticsearch, the search is alread built-in with the collections.

# Installation
`npm install`

# Run the application
`npm start`

# Test 
## Create New Products
```
curl --location --request POST 'localhost:3000/product' \
--header 'Content-Type: application/json' \
--header 'Cookie: fusionauth.sso=AjtVBxAyC2hW0RMdfcThQ56NXuzLENd33DyAWUBYgrAT' \
--data-raw '[
    {
        "id":1,
        "name": "Apple Watch",
        "price": 2000,
        "status": "available",
        "quantity": 10
    },
    {
        "id":2,
        "name": "Iphone 13 Mini",
        "price": 3000,
        "status": "available",
        "quantity": 4
    },
    {
        "id":3,
        "name": "Google Home",
        "price": 2080,
        "status": "available",
        "quantity": 12
    },
    {
        "id":4,
        "name": "Mac Book Pro",
        "price": 25000,
        "status": "available",
        "quantity": 50
    },
    {
        "id":5,
        "name": "Smartbox Router",
        "price": 9000,
        "status": "available",
        "quantity": 30
    }
]'
```

## Get Products using filters
```
curl --location --request GET 'localhost:3000/product' \
--header 'Content-Type: application/json' \
--header 'Cookie: fusionauth.sso=AjtVBxAyC2hW0RMdfcThQ56NXuzLENd33DyAWUBYgrAT' \
--data-raw '{
   "q": "Google",
   "searchFields":["name"],
   "filter":{"price":{"$lt":5000}}
}'
```