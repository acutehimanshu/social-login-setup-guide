# Development vs Production

## Problem

The site works in local testing or staging but fails on the live website.

### What you see

- login works on localhost
- login fails on the live domain
- provider complains about redirect, domain, or app mismatch

### What it usually means

The app was configured for a development environment but the live environment was not added or updated.

### What the client can check

- confirm the live website domain
- check whether a staging or localhost URL is still configured
- review whether the website uses `www` or a different subdomain in production

### What the developer should check

- compare local and live configurations
- confirm production domain and redirect values are correctly registered
- confirm the correct credentials are being used for the live site
- review whether the app has multiple environment settings

### When to contact the provider

Contact the provider only if the live configuration is correct and still rejected.

[Back to Social Login Troubleshooting Center](README.md)
