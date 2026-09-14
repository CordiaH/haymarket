# Security

## Reporting

**Do not open a public issue.** Use GitHub's private vulnerability reporting
(Security tab → Report a vulnerability), or email `security@haymarket.social`.

If you would prefer encrypted contact, the PGP key is published at
`https://haymarket.social/.well-known/security.txt`.

Expect acknowledgement within 72 hours. This project is maintained by one
person, so a full assessment may take longer — you will get a real response
rather than silence.

## What we consider severe here

The usual severity ranking does not quite fit this platform. A bug that leaks
*who is a member* matters more than one that leaks what they posted, because
membership reveals political affiliation and a post may already be public.

In rough order:

1. **Anything that associates a person with the platform without their
   intent.** Enumeration of members, deanonymization through billing records
   or crowdfunding, correlation of an account with a legal identity.
2. **Anything that exposes private group membership or attendee lists.**
   Rosters are private at the database level; a path around RLS is critical.
3. **Anything that breaks Freemarket's encryption**, including key
   substitution, downgrade, or a path that gets plaintext to the server.
4. **Anything that lets a campaign target an individual.** The
   institutions-only constraint is a safety property, not a validation nicety.
5. **Anything that causes member data to be retained past its window** — a
   sweeper that silently stops is a real vulnerability, not an ops issue.
6. Standard web vulnerabilities: XSS, CSRF, SSRF, injection, privilege
   escalation, auth bypass.

## Already known and accepted

Reporting these will not be treated as a finding, though a novel exploitation
path might be:

**Freemarket is a web application, so the server delivers the code.** A
compromised or legally compelled server could serve key-exfiltrating
JavaScript. This is inherent to browser-delivered cryptography. We mitigate
with a separate origin, strict CSP, subresource integrity, and an installable
PWA, and we state the limitation publicly rather than hiding it. Members who
need a stronger guarantee are directed to Signal.

**The server sees group membership and message timing.** End-to-end encryption
protects content, not metadata. We minimize what is stored and retain it
briefly, but we do not claim metadata privacy we cannot deliver.

**Our host and CDN see IP addresses.** Any web service's do. We do not put
them on member records and retention is short.

## Disclosure

We will work with you on a timeline. Default is 90 days or until a fix ships,
whichever comes first. If a vulnerability is being actively exploited we will
move faster and say so publicly.

We will credit you unless you prefer otherwise. There is no bug bounty budget
yet; if that changes, this file changes.

## If you are a member who thinks their account is compromised

Email `security@haymarket.social`. We will not ask you for your password or
recovery codes, and nobody from this project will ever ask you for them over
any channel.
