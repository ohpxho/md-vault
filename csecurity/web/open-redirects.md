# Open Redirect Vulnerability

- This is an exploit to defined urls of a site usually from a query parameter.

Example of vulnerable url:

```
https://example.com/login?redirect=http://evil.com
```

If example.com automatically redirects you to the evil site without validation, then this is a vulnerability.

- Attackers use this vulnerability to abuse the trust of users in the site and redirect them to what they think is legitimate since the domain in the url is legit.
- This vulenrability could be used for:
  1. Phising attacks (emails or sms with the modified link)
  2. Credential Harvesting (fake pages)
  3. Bypassing security (some oauth trust internal redirects, which can be abused to steal tokens)

### Mitigation

1. Allow-list only internal paths
2. Strip domain names
3. Use a fixed set of valid redirect targets

Source:

1. **Real-World Bug Bounty: Chapter 2**
