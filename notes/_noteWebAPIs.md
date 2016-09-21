Web APIs
-----------

> 1×× Informational
> 2×× Success
> 3×× Redirection
> 4×× Client Error
> 5×× Server Error


URI - just identifier

URL - can address, access
> protocol://hostname<:port>/path?querystring

id in  path
- /api/:version/products/:id
- /api/v1/users/:id/profile

Content-Type aka media type, MIME type
- Content-Type: text/html; charset=UTF-8 (response)
  - text/html
  - text/plain
  - text/css
  - text/javascript
  - zip, pdf, png, sound, video
- charset
  - UTF-8
  - ISO-8859-1
- Content-Type: application/json; charset=utf-8 (request) or xml

## REST
(representational state transfer)

Create, POST,   /profiles, params {"name": "jamie"}
Read,   GET,    /profiles/:1
Update, PUT,    /profiles/:1, params {"name": "JW"}
Delete, Delete, / profiles/:1

> Verb + Resource

### Fetching
- a collection /v1/blogs/posts
- a single element /v1/blogs/posts/2


### Request
- HTTP requests include a path, method, headers, and body.
- GET, w/o body, to query
- POST w body, to create
- PUT w body, to Update
- DELETE
- readonly - GET
- read and wirte - POST, PUT, DELETE
- The Accept header tells the provider what media types can be used to respond to the request.

```ini
GET http://book-example.herokuapp.com/v1/products/1 Accept:application/json
GET /v1/products/1 HTTP/1.1
Accept: application/json
Accept-Encoding: gzip, deflate
Host: book-example.herokuapp.com
User-Agent: HTTPie/0.8.0
```
book-example.herokuap.com/v1/products


### response

header
  - Access-Control-Allow-Origin: *
  - Allow: GET, HEAD
  - Content-Length: 1984
  - Content-Type: application/json; charset=utf-8
  - ETag: "6df23dc03f9b54cc"
  - Last-Modified: Thu, 05 Jul 2012 15:31:30 GMT
  - WWW-Authenticate: Basic
  - X-* Headers
    X-RateLimit-Limit: 60
    X-RateLimit-Remaining: 57
    X-RateLimit-Reset: 1413592144
    

### Twitter APIs

REST conventions
GET and POST only


[] exercise retweat, geo location, ...

Rest anti-patterns
====================

- URL should tell the story
  - V: POST /accounts/4402278/close
  - X: POST /accounts/close
       POST /closeAccount

- Verbs
  - GET - read
  - POST - Create 
  - PUT - Update whole records
  - PATCH - Updates pieces of records
  - DELETE

  - V: DELETE /accounts/4402278
  - X: POST /accounts/4402278/delete

- Idempotency
  - Idempotent methods: GET, PUT, OPTIONS
  - Non Idempotent methods: POST


- Status codes

2xx - Success	
- 200 OK		
- 201 Created	
- 203 Partial Information
- 204 No response		
- 404 Not Found	

3xx - Redirection
- 301 Moved
- 302 Found
- 304 Not Modified

4xx / 5xx - Error	
- 400 Bad Request
- 401 Unauthorized	
- 402 Payment Required	
- 403 Forbidden
- 500 Internal Server Error	
- 503 Service Unavailable	


- hypermedia
  - JSON + Links + URLs + Forms/Queries



- HATEOAS