# Client FAQ for Social Login Setup

This page answers the common questions non-technical clients usually ask when a developer requests social login credentials.

[Back to main README](../README.md)

## 1. What is a Client ID?

**Simple answer:** A Client ID is usually a public identifier that tells a provider which app or website is asking for login.

**Why it matters:** It identifies the app to the provider, but it is not the same as a password or secret.

**Relevant guides:** [Google guide](google/README.md), [Apple guide](apple/README.md), [Facebook guide](facebook/README.md)

## 2. Why does my developer need it?

**Simple answer:** The developer needs it so the website can connect to the correct provider app and open the login flow.

**Why it matters:** Without the correct identifier, the website may not know which app or project to use.

## 3. Where do I get it?

**Simple answer:** You usually get it from the provider’s developer dashboard for the app or project created for your website.

**Why it matters:** The value must come from the correct provider app and the correct environment, such as production or testing.

## 4. Is Client ID a password?

**Simple answer:** No. A Client ID is not a password.

**Why it matters:** It is usually an identifier, not a secret. Passwords, OTP codes, and private keys must stay private.

## 5. Can I share my Client ID?

**Simple answer:** Usually yes, if your developer asks for it as part of the setup.

**Why it matters:** It is normally meant to be shared with the developer or configured in the website, but it is still not a secret like a password or private key.

## 6. Should I share my password?

**Simple answer:** No.

**Why it matters:** Your provider account password should never be shared with a developer unless a provider specifically requires it through a secure, trusted process.

## 7. Should I share my OTP?

**Simple answer:** No.

**Why it matters:** OTP codes, two-factor codes, and recovery codes are sensitive security values and should not be shared in a public ticket, email, or document.

## 8. What is a Client Secret?

**Simple answer:** A Client Secret is a sensitive credential used to securely confirm that an app is allowed to communicate with the provider.

**Why it matters:** It is a secret, not a public identifier, and it should be kept private.

## 9. Why does my developer need a Redirect URI?

**Simple answer:** The provider needs to know where to send the user after login is complete.

**Why it matters:** If the redirect URI does not match exactly, the login flow can fail.

**Relevant guide:** [Redirect URI troubleshooting](../troubleshooting/redirect-uri.md)

## 10. What is a callback URL?

**Simple answer:** A callback URL is the page where the provider sends the user back after login.

**Why it matters:** It is the return point for the login flow and must match the exact value that the app is configured to use.

## 11. Why does my developer give me a URL?

**Simple answer:** Because the provider app must be configured to allow login from the correct website and return users to the proper page.

**Why it matters:** The developer tells you the exact value so you can enter the correct URL and avoid a mismatch.

## 12. Why do Google, Apple and Facebook work differently?

**Simple answer:** Each provider has its own dashboard, app setup, and terminology.

**Why it matters:** They all solve the same problem in broadly similar ways, but the required values and setup flow are not identical.

**Relevant guides:** [Google guide](google/README.md), [Apple guide](apple/README.md), [Facebook guide](facebook/README.md)

## 13. Why does Apple ask for more information?

**Simple answer:** Apple often requires more setup details because its sign-in flow includes additional identifiers and secure key material.

**Why it matters:** The extra data is often tied to app ownership, domain verification, and secure server-side configuration.

**Relevant guide:** [Apple guide](apple/README.md)

## 14. Why does Facebook have Development and Live modes?

**Simple answer:** Facebook may separate testing mode from live production mode so apps can be tested before being used publicly.

**Why it matters:** An app may work in testing but fail in production if the wrong app mode or environment is being used.

**Relevant guide:** [Facebook guide](facebook/README.md)

## 15. Why does login work on one domain but not another?

**Simple answer:** The provider usually checks the exact domain, subdomain, and redirect value.

**Why it matters:** A local site, staging site, or live site may each require separate configuration.

**Relevant guide:** [Development vs production troubleshooting](../troubleshooting/development-vs-production.md)

## 16. Can I use my personal account?

**Simple answer:** Sometimes, but it is usually better to use a business or project account when possible.

**Why it matters:** Using the right account helps avoid confusion if the app later changes ownership or the original account becomes unavailable.

## 17. Who should own the provider application?

**Simple answer:** The client or business usually owns the provider app, while the developer implements the website integration.

**Why it matters:** The app should belong to the project or company that controls the website, not to an individual who may leave the project later.

## 18. What happens if I lose access to the account?

**Simple answer:** The website login may stop working until the correct account owner restores access or transfers ownership.

**Why it matters:** This is why the app should be tied to a reliable business or project account whenever possible.

## 19. What should I do if I see an error?

**Simple answer:** Check the exact domain, redirect URI, app name, and environment first, then contact your developer with the full error and the website URL.

**Why it matters:** Many login errors are caused by a mismatch rather than a serious provider issue.

**Relevant guide:** [Social Login Troubleshooting Center](../troubleshooting/README.md)

## 20. What information should I send my developer?

**Simple answer:** Send the exact provider app identifier or credential the developer requested, plus the real website URL, domain, and environment.

**Why it matters:** Do not send passwords, OTP codes, recovery codes, private keys, or other secrets unless the developer specifically requests them through a secure process.

**Useful templates:** [Client credential request](../templates/client-credential-request.md), [Redirect URL checklist](../templates/redirect-url-checklist.md), [Client handover](../templates/client-handover.md)

---

## Quick reminder

- A Client ID is usually a public identifier.
- A Client Secret is a sensitive secret.
- A Redirect URI is the exact address the provider sends the user back to.
- Never share passwords, OTP codes, recovery codes, private keys, access tokens, or refresh tokens in a public document or message.

[Back to main README](../README.md)
