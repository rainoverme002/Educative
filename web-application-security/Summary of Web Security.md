# Summary of Web Security

## Understanding Browser

- It’s a bad idea to support as many browsers as possible

### Browser job

Long story short, a browser’s job consists of:

- DNS resolution (The process of resolving a hostname from a given IP.)
- HTTP exchange (a way for the browser to communicate to the server what it wants, and for the server to reply back)
- Rendering
- Rinse and repeat

### Browser for developer

- cURL (HTTP exchange on-the-fly by sending an HTTP request from our command line)

```bash
curl -I educative.io
curl -I -v educative.io
```

## HTTP

### How HTTP Works

An HTTP message (either a request or a response) contains multiple parts:

- start line
- headers
- body

```bash
# header

GET /players/lebron-james HTTP/1.1
Host: nba.com
Accept: */*
Coolness: 9000

# response

HTTP/1.1 200 OK
Content-Type: application/json
Cache-Control: private, max-age=3600

{"name": "Lebron James", "birthplace": "Akron, Ohio", ...}
```

### HTTP vs HTTPS vs H2

- HTTPS was aimed at improving the security
- HTTPS (HTTP Secure) aims to let clients and servers talk securely through TLS (Transport Layer Security)
- H2 was geared towards speeding the process up and uses binary rather than plaintext messages

How to secure HTTP?

- authentication: ensuring you’re actually talking to your significant other and not someone pretending to be them.
- encryption: communicating the password without your coworkers being able to understand it and write it down.

### Mechanics of encryption

- Caesar chiper (simple)
- Diffie-Hellman key exchange protocol (real application)

### GET vs POST

- GET requests usually don’t carry a body, so parameters are included in the URL (i.e., www.example.com/articles?article_id=1)
- GET will not change server state
- POST requests are generally used to send (“post”) data which is included in the body
- POST might change server state

Sending data in the body is safer than in URL

- POST is safer than GET
