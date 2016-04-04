# graphql-intro

# A minimal introduction and working example of graphql

(based on http://www.kejik.com/article/72415.html)


# How to run

1. npm install
2. nodemon index.js
3. try following requests: 

````shellscript
$ curl -v -XPOST -H "Content-Type:application/graphql" -d '{__schema {queryType {name, fields {name, description}}}}' http://localhost:3000/graphql
*   Trying ::1...
* Connected to localhost (::1) port 3000 (#0)
> POST /graphql HTTP/1.1
> Host: localhost:3000
> User-Agent: curl/7.43.0
> Accept: */*
> Content-Type:application/graphql
> Content-Length: 57
> 
* upload completely sent off: 57 out of 57 bytes
< HTTP/1.1 200 OK
< X-Powered-By: Express
< Content-Type: text/html; charset=utf-8
< Content-Length: 220
< ETag: W/"dc-ivZt2badUlk+ZGGokrqU5g"
< Date: Mon, 04 Apr 2016 23:13:07 GMT
< Connection: keep-alive
< 
{
  "data": {
    "__schema": {
      "queryType": {
        "name": "RootQueryType",
        "fields": [
          {
            "name": "count",
            "description": null
          }
        ]
      }
    }
  }
* Connection #0 to host localhost left intact
}

$curl -v -XPOST -H "Content-Type:application/graphql" -d 'query RootQueryType {count}' http://localhost:3000/graphql
*   Trying ::1...
* Connected to localhost (::1) port 3000 (#0)
> POST /graphql HTTP/1.1
> Host: localhost:3000
> User-Agent: curl/7.43.0
> Accept: */*
> Content-Type:application/graphql
> Content-Length: 27
> 
* upload completely sent off: 27 out of 27 bytes
< HTTP/1.1 200 OK
< X-Powered-By: Express
< Content-Type: text/html; charset=utf-8
< Content-Length: 34
< ETag: W/"22-fv2a+GP3ENbCXJfKNUYd6w"
< Date: Mon, 04 Apr 2016 23:13:24 GMT
< Connection: keep-alive
< 
{
  "data": {
    "count": 0
  }
* Connection #0 to host localhost left intact
}

$curl -v -XPOST -H "Content-Type:application/graphql" -d 'mutation RootMutationType {updateCount}' http://localhost:3000/graphql
*   Trying ::1...
* Connected to localhost (::1) port 3000 (#0)
> POST /graphql HTTP/1.1
> Host: localhost:3000
> User-Agent: curl/7.43.0
> Accept: */*
> Content-Type:application/graphql
> Content-Length: 39
> 
* upload completely sent off: 39 out of 39 bytes
< HTTP/1.1 200 OK
< X-Powered-By: Express
< Content-Type: text/html; charset=utf-8
< Content-Length: 40
< ETag: W/"28-VC9Ac772twW2ejARmzoWZg"
< Date: Mon, 04 Apr 2016 23:13:28 GMT
< Connection: keep-alive
< 
{
  "data": {
    "updateCount": 1
  }
* Connection #0 to host localhost left intact
}mdm:graphql-intro xma$ curl -v -XPOST -H "Content-Type:application/graphql" -d 'mutation RootMutationType {updateCount}' http://localhost:3000/graphql
*   Trying ::1...
* Connected to localhost (::1) port 3000 (#0)
> POST /graphql HTTP/1.1
> Host: localhost:3000
> User-Agent: curl/7.43.0
> Accept: */*
> Content-Type:application/graphql
> Content-Length: 39
> 
* upload completely sent off: 39 out of 39 bytes
< HTTP/1.1 200 OK
< X-Powered-By: Express
< Content-Type: text/html; charset=utf-8
< Content-Length: 40
< ETag: W/"28-MVSA9CNSY62sw6VhOh+g4w"
< Date: Mon, 04 Apr 2016 23:13:29 GMT
< Connection: keep-alive
< 
{
  "data": {
    "updateCount": 2
  }
* Connection #0 to host localhost left intact

