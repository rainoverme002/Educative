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

## Protecting through HTTP Headers

- HTTP header allowed to specify how a particular resource should be read, cached or secured

### HSTS

- HSTS policy is a trust on first use mechanism, make the browser knows that subsequent interactions must use HTTPS

### HPKP (Dangerous and has been deprecated)

- a trust on first use mechanism like HSTS
- HTTP Public Key Pinning, a mechanism that allows us to advertise which SSL certificates to expect when a browser connects to our servers

How HPKP look like

```bash
Public-Key-Pins:
  pin-sha256="9yw7rfw9f4hu9eho4fhh4uifh4ifhiu=";
  pin-sha256="cwi87y89f4fh4fihi9fhi4hvhuh3du3=";
  max-age=3600; includeSubDomains;
  report-uri="https://pkpviolations.example.org/collect"
```

### Expect-CT

- Expect-CT is to inform the browser that it should perform additional background checks to ensure the certificate is genuine

```bash
Expect-CT: max-age=3600, enforce, report-uri="https://ct.example.com/report"
```

### X-Frame-Options

- XFO lets you decide whether your app can be embedded as an iframe on external websites
- iframe is usually use to clickjacking attack

```bash
HTTP/1.1 200 OK
Content-Type: application/json
X-Frame-Options: DENY
```

### Content-Security-Policy

[Github CSP](https://github.blog/2016-04-12-githubs-csp-journey/)

[Github Post CSP](https://github.blog/2017-01-19-githubs-post-csp-journey/)

- a next-generation utility belt for preventing a plethora of attacks, ranging from XSS (cross-site scripting) to clickjacking.

```bash
curl -I "https://x6jr4kg.educative.run/?search=%3Cscript+type%3D%22text%2Fjavascript%22%3Ealert%28%27You%20have%20been%20PWNED%27%29%3C%2Fscript%3E&csp=on"

#output
HTTP/1.1 200 OK
X-XSS-Protection: 0
Content-Security-Policy: default-src 'self'
Date: Sat, 11 Aug 2018 10:46:27 GMT
Connection: keep-alive
```

### X-XSS-Protection

- Superseded by CSP
- can be used to mitigate XSS attacks.
- This header is used to mitigate XSS attacks in older browsers that don’t fully support CSP

### Feature-Policy

```bash
Feature-Policy: vibrate 'self'; push *; camera 'none'

# allow the current page to use the vibration API
# can use the push notification API.
# the camera API is denied
```

### X-Content-Type-Options

- MIME-sniffing, a browser feature to auto-detect (and fix) the content type of a resource it is downloading
- header that completely disables MIME-sniffing

```bash
X-Content-Type-Options: nosniff
```

### Cross origin resource sharing (CORS)

- a set of directives that allow you to execute cross-domain requests
- to avoid cookies stealing
- You can use proxy also to do the same thing

```bash
Access-Control-Allow-Origin: *

# whitelisting
Access-Control-Allow-Origin: https://example.com
```

### X-Permitted-Cross-Domain-Policies & Referrer-Policy

- X-Permitted-Cross-Domain-Policies like CORS, but for Adobe products, namely Flash and Acrobat
- Referrer-Policy could pose a potential threat to our users’ privacy because it would specify which domains the users came from

### Reporting API

[Check Security Header](https://securityheaders.com)

- allows a website to advertise to the browser a particular URL it expects to receive reports to
