Version: NAFATH-V1
Track: AI

## Overview

A national login service connects citizens to many government services through one mobile app and website. Software standards determine how each service requests sign-in and limited access. The mobile app must request only necessary device permissions at the moment a feature needs them. Network protections can reduce exposure of DNS lookups, while phishing-resistant authentication helps stop stolen credentials from being reused. An AI risk model may flag unusual login patterns, but its errors and impacts need careful governance. Because identity records are sensitive, data handling must follow Oman's applicable privacy rules and government policy. For AI, the key question is how to manage risks before using a model to flag suspicious logins.

## Software

OAuth 2.0 is an authorization framework: it lets a client obtain scoped access tokens for protected resources. It does not define a standard way to tell a client who the user is. OpenID Connect adds an identity layer on OAuth 2.0, so a relying party can verify the authenticated user through an ID Token. For a shared government login, OIDC supports sign-in; OAuth access tokens authorize permitted API access.
Resource: OpenID Connect Core 1.0 - https://openid.net/specs/openid-connect-core-1_0.html

## AI

NIST's AI Risk Management Framework calls for governing, mapping, measuring, and managing risks across an AI system's lifecycle. Before a login flagger goes live, define accountability and intended use; assess privacy, security, reliability, and fairness risks; test false positives and false negatives across relevant groups; document limits and human oversight; and plan monitoring, appeals, incident response, and safe rollback. Reassess as data and attacks change.
Resource: NIST AI RMF Core - https://airc.nist.gov/airmf-resources/airmf/5-sec-core/

## Mobile

Android apps run in a limited-access sandbox. A login app can access its own data without asking for a runtime permission, but sensitive device resources outside that sandbox may require one. The app should request a dangerous permission only when the user starts the feature that needs it, explain why where appropriate, check the user's choice, and continue gracefully if permission is denied.
Resource: Request runtime permissions - https://developer.android.com/training/permissions/requesting

## Networking

DNS over HTTPS (DoH) sends DNS queries and replies through HTTPS, encrypting them between the app or device and its chosen resolver. This can hide DNS lookups from observers on the local network and the internet provider. It does not hide them from the DoH resolver, conceal the user's IP address from contacted services, or encrypt all other traffic; timing and destination IPs may still reveal activity.
Resource: RFC 8484 - DNS Queries over HTTPS (DoH) - https://datatracker.ietf.org/doc/html/rfc8484

## Cybersecurity

Phishing-resistant MFA binds authentication to the legitimate service so a fake site cannot simply relay a reusable code. FIDO/WebAuthn and PKI-based public-key methods can be phishing-resistant when cryptographically bound to the real service. SMS codes, authenticator-app OTPs, and ordinary push approvals do not qualify because a fake verifier can relay them. Number matching helps reduce push fatigue, but does not bind a code to the genuine service.
Resource: NIST SP 800-63B - Authentication and Authenticator Management - https://pages.nist.gov/800-63-4/sp800-63b/authenticators/

## Data

Oman's Personal Data Protection Law (Royal Decree 6/2022) excludes state administrative units and other public legal entities; MTCIT says a separate Personal Data Protection Policy under Circular 6/2024 governs those units. The authority should therefore follow that policy's rules for lawful, necessary collection, clear notice and consent, security controls, protected storage, and handling of disclosure or breaches. Confirm the authority's exact status and applicable retention and transfer rules before launch.
Resource: Personal Data Protection - MTCIT - https://www.mtcit.gov.om/sectors/governance/personal

## Misconception in My Track

A common misconception is that a model that performs well in a historical test can safely block suspicious logins automatically. NIST's AI RMF instead treats risk work as continuous: teams must understand the deployment context, evaluate reliability, privacy, security, and fairness, and monitor the system after launch. A safer first use is to flag cases for trained human review, measure false positives and missed attacks, and provide a way to challenge harmful outcomes. In “5.3 Measure,” NIST states: “AI systems should be tested before their deployment and regularly while in operation.”

## Open Question

What false-positive rate and human-review process would protect citizens from account lockouts while still catching emerging attacks?
Version: NAFATH-V1
Track: AI

## Overview

A national login service connects citizens to many government services through one mobile app and website. Software standards determine how each service requests sign-in and limited access. The mobile app must request only necessary device permissions at the moment a feature needs them. Network protections can reduce exposure of DNS lookups, while phishing-resistant authentication helps stop stolen credentials from being reused. An AI risk model may flag unusual login patterns, but its errors and impacts need careful governance. Because identity records are sensitive, data handling must follow Oman's applicable privacy rules and government policy. For AI, the key question is how to manage risks before using a model to flag suspicious logins.

## Software

## AI

## Mobile

## Networking

## Cybersecurity

## Data

## Misconception in My Track

## Open Question
Version: NAFATH-V1
Track: AI

## Overview

## Software

## AI

## Mobile

## Networking

## Cybersecurity

## Data

## Misconception in My Track

## Open Question
