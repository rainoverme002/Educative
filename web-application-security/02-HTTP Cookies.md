# HTTP Cookies

- standardize sort of mechanism to implement sessions
- contains small bits of data, the browser stores it and sends it along with future requests to the same server.
- extremely sensitive (store session IDs or access tokens)

## Mechanism

1. Server send cookies (can set multiple cookies)

    ```bash
    HTTP/1.1 200 Ok
    Set-Cookie: access_token=1234
    Set-Cookie: user_id=10
    ...
    ```

2. Client store it and send it subsequent request (can set multiple cookies)

    ```bash
    GET / HTTP/1.1
    Host: example.com
    Cookie: access_token=1234; user_id=10
    ...
    ```

### Additional Directive

- Expires (a cookie should expire)
- Max-Age specifies the number of seconds until the cookie should expire
- Domain (which hosts the cookie should be sent to)
- Path (same like domain but for URL path)
- Secure (encrypted cookies)
- HttpOnly (JS can't read cookies)
- SameSite (CSRF attack prevention)

#### Host-only

- its validity is restricted to the current domain only.

## Session vs persistent cookies

- Persistent cookie (stored on the client until the deadline set by its Expires or Max-Age directives.)
- Session cookie (sends a cookie without setting its Expires or Max-Age and browser will delete it when it shuts down)

### Session restoring

- Browsers let users resume a session after a crash

## Supercookies

- set a cookie on a top-level domain (TLD) such as .com or .org

Security concern:

1. user privacy: every website running on that specific TLD would be able to track information about the user in shared storage
2. information leakage: a server could mistakenly store a sensitive piece of data in a cookie available to other sites

## Encrypt it Or Forget it

- session hijacking attacks usually happen through a man-in-the-middle
- we can use HTTPS when issuing the cookie and add the Secure flag to it

## Protect your Cookies

- you could read the contents of the cookie jar with a simple document.cookie
- HttpOnly flag (making impossible to access the cookie via JS)

## SameSite CSRF Killer

- SameSite (the browser will first check whether the origin of the request is the same origin that issued the cookie)
- Prevent CSRF (an unwanted request made by site A to site B while the user is authenticated on site B) attack

## localStorage (Cookies alternative)

- place to store sensitive tokens
- But, localStorage does not offer any kind of protection against XSS attacks

### JWT

- a way to securely exchange data between two clients
- you could store a JWT in a cookie, localStorage or even in memory 
