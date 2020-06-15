# Multi-factor authentication(MFA)

## What is MFA?

Multi-factor authentication is an authentication method in which a computer user is granted access only after successfully presenting two or more pieces of evidence (or factors) to an authentication mechanism: knowledge (something the user and only the user knows), possession (something the user and only the user has), and inherence (something the user and only the user is).[1]

### Two-factor authentication(2FA)

Two-factor authentication is a typical type, or subset, of multi-factor authentication. It is a method of confirming users' claimed identities by using a combination of two different factors: 1) something they know, 2) something they have, or 3) something they are.

### Adaptive authentication

This type of MFA takes context into account to flag logins that are out of the ordinary. When a person tries to authenticate in an unusual context, Adaptive MFA may tighten security by requesting additional credentials. For example, if a user is logging in from a cafe late at night—and this is not typical for that user—the MFA tool may require the user to enter a code texted to the user’s phone.

![.](https://www.onelogin.com/assets/img/learn/adaptive-mfa.svg)


## How does MFA work?

MFA verifies a user’s identity by requiring multiple credentials. It is a critical component of identity and access management (IAM). Rather than just asking for a username and password, MFA requires other—additional—credentials, such as a code from the user’s smartphone, the answer to a security question, a fingerprint, or facial recognition.

![.](https://www.onelogin.com/assets/img/learn/high-level-mfa.svg)


## Application of MFA on mobile devices

Application of MFA on mobile devices includes push-based authentication, QR code based authentication, one-time password authentication (event-based and time-based), and SMS-based verification. SMS-based verification suffers from some security concerns. Phones can be cloned, apps can run on several phones and cell-phone maintenance personnel can read SMS texts. Not least, cell phones can be compromised in general, meaning the phone is no longer something only the user has.

### Advantages



(1) As they are constantly changed, dynamically generated passcodes are safer to use than fixed (static) log-in information.

(2) Depending on the solution, passcodes that have been used are automatically replaced in order to ensure that a valid code is always available, transmission/reception problems do not therefore prevent logins.

### Drawbacks

(1) Users may still be susceptible to cyber attacks. An attacker can send a  message that links to a spoofed website that looks identical to the actual website. The attacker can then get the authentication code, user name and password.

(2) Account recovery typically bypasses two-factor authentication.

## Bibliography

[1]  [Two-factor authentication: What you need to know (FAQ) – CNET]( https://www.cnet.com/news/two-factor-authentication-what-you-need-to-know-faq/)

[2] [Attackers breached the servers of RSA and stole information that could be used to compromise the security of two-factor authentication tokens used by 40 million employees (register.com, 18 Mar 2011)](https://www.theregister.com/2011/03/18/rsa_breach_leaks_securid_data/)
