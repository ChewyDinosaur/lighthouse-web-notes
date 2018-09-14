## HTTP and APIs

# An HTTP Request Walks Into a Browser...

Today's lecture is going to be about finding more and more specific answers to one question:

What happens when you type google.ca into your browser?

## Muggle's Answer

A web page loads.

## Slightly Less Muggly Answer

Your browser makes an HTTP Request, and some server somewhere makes an HTTP Response.

### Wait... what's HTTP?

Hypertext Transfer Protocol. Sent on the TCP / IP

Other protocols that often go on the TCP/IP

* FTP - File Transfer Protocol
* SMTP - Simple Mail Transfer Protocol
* POP(3) - Post Office Protocol
HTTP Messages generally have:

* Headers - Key-Value Pairs of info
* Body (optional) - Block of data
* HTTP is a request-response model
* HTTP is stateless 
* HTTP is resource-based

## HTTP Requests

### HTTP Methods

* GET - read-only
* POST - for making changes
* PUT - updates a resource by replacing it (or some fields of it)
* DELETE - deletes a resource
* PATCH - updates a resource by defining changes (no one can agree on what that means)
The strange limitations of HTML confine us to GET and POST this week. That will not always be the case.

### URL

Protocol: 'http://' Domain: localhost:1234 URI: /poodles

From Browser
```
GET / HTTP/1.1
Host: localhost:1234
Connection: keep-alive
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/68.0.3440.106 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8
Accept-Encoding: gzip, deflate, br
Accept-Language: en-US,en;q=0.9,la;q=0.8
Cookie: csrftoken=k3nJ4rHhKCGqq8jNCLbXU78QxVeLNpbHZR5ldOQKrHNOUiXFG4CSYHGTEbme6SeJ; sessionid=xpynmlt9dbh7zblsxuopuo4p45cmdync; _ga=GA1.1.1246153238.1535571637; _compass_session=WEhtaWdWNzFZOW9WN3FjdFJUYzZ3WG1Nc1FlVjlSMVo2ZkRySzI1SWtoMFlFbFZZNktTNHM2bUJWNHhLWmxPeWhuMks2eHBLWVFDM2NGY3cxN3MrNkYzbVpRTUh2cFZ3NDBuQ0I0c1JxTStENlVCR1RPbm8rYmxlNG9VSUJWZkIvUlFqNklCQnM5Y240VGx0aHNqeGd3d2MyWTVKVWFUTmpyNDJMdWJBRTZ1ZmQ0RUN5UUs3WW1RY3VveDlzaEpJZnNEU1BDdzdQUnAvaHpIYVBTaVVMZz09LS0wNXJaSHhZT2o3QnZVWXhKZm9ZbWd3PT0%3D--8d6e2d75a1f7525c95eadfeb6f3c902fba171381; io=klZoleO4afN7XD4VAAAA
```
From CURL
```
GET / HTTP/1.1
Host: localhost:1234
User-Agent: curl/7.60.0
Accept: */*
```
From CURL
```
POST /login HTTP/1.1
Host: localhost:1234
User-Agent: curl/7.60.0
Accept: */*
Content-Length: 9
Content-Type: application/x-www-form-urlencoded

name=joel
```
## HTTP Responses

### Status Codes

* 100 - Networky dark magics
* 200 - OK
* 300 - Redirection
* 400 - Client Error
* 500 - Server Error
```
HTTP/1.1 200 OK
server: ecstatic-1.4.1
Content-Type: text/html
etag: "8617847895-96-"2018-09-03T16:52:08.381Z""
last-modified: Mon, 03 Sep 2018 16:52:08 GMT
cache-control: max-age=3600
Date: Mon, 03 Sep 2018 16:54:49 GMT
Connection: keep-alive
```
Image
```
HTTP/1.1 200 OK
server: ecstatic-1.4.1
last-modified: Mon, 03 Sep 2018 16:57:07 GMT
etag: "8617848040-48377-"2018-09-03T16:57:07.284Z""
cache-control: max-age=3600
content-length: 48377
content-type: image/jpeg; charset=utf-8
Date: Mon, 03 Sep 2018 16:57:37 GMT
Connection: keep-alive
```
404
```
HTTP/1.1 404 Not Found
server: ecstatic-1.4.1
Date: Mon, 03 Sep 2018 16:59:55 GMT
Connection: keep-alive
Content-Length: 0
```
## But... how does it know where to go?

### DNS (Domain Name Server)

# Node API demo
For this demo, we wrote a small app to connect to Spotify and search for artists.
[Gist](https://mandrillapp.com/track/click/30244704/gist.github.com?p=eyJzIjoiajZxNmpoRGtUaExKZDhUWGt3NzV5WG92U29jIiwidiI6MSwicCI6IntcInVcIjozMDI0NDcwNCxcInZcIjoxLFwidXJsXCI6XCJodHRwczpcXFwvXFxcL2dpc3QuZ2l0aHViLmNvbVxcXC9Kb2VsQ29kZXNcXFwvMGYxZTY4ZTkzZjVhZjBhN2Q1ZWExZGFjMWZmNDc1MjlcIixcImlkXCI6XCI4MTUyMDE4YWViNWM0Y2NiODZjMzQxNDljMmFlZmIzN1wiLFwidXJsX2lkc1wiOltcIjA0OGFmMTY1ZjgzNTdmYjVmZDBhNTFhNzUyMTQwYjA3YWRmM2UyNTRcIl19In0)
