# Situationals: Choice in Security

## Blacklisting vs Whitelisting

- the choice of utilizing a blacklist or a whitelist depends on the context you’re operating in
- whitelisting is a better approach but is often impractical
- blacklisting problem is hard to know everything that’s going to hurt us

## Logging Secrets

- Having the whole request logged is helpful but we must be aware that it will also lead to storing auth tokens
- The solution is to simply avoid logging sensitive information, by Whitelist what you log and also masking.
- Don't logging sensitive data

## Never Trust the client

- never trust the client and prevent them from being able to easily tamper with the data you’ve handed off

### Are JWTs safe?

- Not really, there is a [JWT Cracker](https://github.com/lmammino/jwt-cracker)

## Generating Session IDs

- Using incremental session IDs is a bad choice
- We would be to use a cryptographically secure function that generates a random string

## Prevent SQL Injection

- Sanitize data before feeding it to a database

## Dependencies With Known Vulnerabilities

- If we use dependencies like external libraries, we need to following up on every updates
- We can use internal command or external service to scan known vulnerabilities.

## Security in Stateless Architecture

- JWT, allow stateless authentication between the client and the server
- Need to balance statelessness (performance) and statefulness (more control), It can be achieved by implementing a mechanism whereby the user can revoke all previous issued token

How to minimizing database hits?

- We can use two tokens, a long-lived one and a short-lived one

## CDN also has a risk

- Attacker can have login credential for your CDN provider's portal
- They can modify your static assets and injecting malicious code

How to Protect user from it?

- [sub-resource integrity](https://developer.mozilla.org/en-US/docs/Web/Security/Subresource_Integrity) (SRI) allows you to check the integrity of your static asset

## OWASP

- [OWASP Cheat Sheet Series](https://cheatsheetseries.owasp.org)
- [OWASP Developer Guide](https://github.com/OWASP/DevGuide)
- [OWASP Testing Guide](https://www.owasp.org/index.php/OWASP_Testing_Guide_v4_Table_of_Contents)
