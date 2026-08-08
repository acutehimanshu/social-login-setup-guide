# Social Login Credential Request

Hello,

To enable social login on the website, we need to set up the relevant provider app and return the required credentials for the website configuration.

Please complete the setup for the provider(s) you want enabled and return the requested value(s) below.

> Please do not send passwords, 2FA codes, recovery codes, or any other private account credentials unless the developer specifically requests them through a secure channel.

## Project Information

### Website

```text
[Website URL or project name]
```

### Environment

```text
Production / Staging / Local development
```

### Developer contact

```text
Developer name:
Email:
Project contact:
```

---

## Provider Required

### Google

**Setup guide:** [Google Login Setup](../docs/google/README.md)

**Information the developer should provide to the client:**

- website URL
- production domain
- redirect URI or callback URL
- any required JavaScript origin values if applicable

**Credential the client should return:**

```text
GOOGLE_CLIENT_ID=
```

**Do not send unless specifically requested by the developer:**

- Google password
- 2FA codes
- recovery codes
- client secret in a public message

---

### Apple

**Setup guide:** [Apple Sign in with Apple Setup](../docs/apple/README.md)

**Information the developer should provide to the client:**

- website URL
- production domain
- return URL or callback URL
- domain verification details if required
- service configuration required by the developer

**Credential the client should return:**

```text
APPLE_CLIENT_ID=
```

**Do not send unless specifically requested by the developer:**

- Apple account password
- Apple ID verification codes
- private key in a public message
- team or account credentials not requested by the developer

---

### Facebook

**Setup guide:** [Facebook Login Setup](../docs/facebook/README.md)

**Information the developer should provide to the client:**

- website URL
- production domain
- redirect URI or callback URL
- app configuration details required for the website

**Credential the client should return:**

```text
FACEBOOK_CLIENT_ID=
```

**Do not send unless specifically requested by the developer:**

- Facebook password
- 2FA codes
- app secret in a public message
- account credentials not requested by the developer

---

## Response to Return

Please return the relevant values in this format:

```text
Google:
GOOGLE_CLIENT_ID=

Apple:
APPLE_CLIENT_ID=

Facebook:
FACEBOOK_CLIENT_ID=
```

If the developer requested additional provider-specific credentials, send only those values and only through the secure method provided by the developer.

## Final Note

The client should never send passwords, OTP codes, recovery codes, private keys, access tokens, refresh tokens, or other sensitive account credentials in a public or shared document. If an issue is unclear, the client should contact the developer before sending any credential or secret.
