# Haymarket Social

An organizing platform. Find each other, decide things together, hold
institutions accountable — without creating a record that can be used against
you.

**License:** AGPL-3.0-or-later · **Status:** pre-launch · [Mission](MISSION.md)
· [Charter](CHARTER.md) · [Security](SECURITY.md)

---

## What this is

A social platform built for organizing rather than for attention. No
behavioral advertising, no data sales, no engagement optimization. Revenue
comes from organizations with budgets, never from the people using it. See
[MISSION.md](MISSION.md) for what that commits us to and
[CHARTER.md](CHARTER.md) for how it is enforced in the code.

## Repositories

| Repo | License | What |
|---|---|---|
| `haymarket-social` | AGPL-3.0-or-later | This repo. The platform. |
| `freemarket` | AGPL-3.0-or-later | Encrypted messaging client (MLS). Separate origin, separate pipeline, stricter review. |
| `haymarket-router` | MIT | Agent orchestration and deploy gating. General-purpose; unencumbered on purpose. |

## Why AGPL

The platform's central claim is about what it *does not* collect. That claim
is only checkable if the code is readable, and only durable if modified
versions have to stay readable too.

The GPL's obligations trigger on distribution, which means someone could run
a modified Haymarket as a service, strip the privacy guarantees, and owe
nobody anything — because they never distributed it. AGPL section 13 closes
that: interacting with the software over a network triggers the source
obligation.

If you run a modified version of this, your users are entitled to your source.
That is the deal, and it is the point.

The name is a separate matter. A license governs code, not trademarks. You may
fork this freely; you may not ship it under this name.

## Privacy properties worth knowing about

Not aspirations. Things you can verify by reading the schema:

- No phone or SMS authentication path exists. Passkeys, TOTP, recovery codes.
- No precise location on any person record. Events carry addresses; people do
  not.
- No sender column on encrypted messages. MLS authenticates the sender inside
  the ciphertext, so "every message sent by user X" is not a query this
  database can answer — for us or for anyone who compels us.
- No presence, no read receipts, no server-side message search.
- Retention enforced by a scheduled sweeper, not by policy.
- Campaign targets constrained to institutions by database check constraint.
- No third-party JavaScript on any page. Every external service disclosed at
  `/services`.

## Stack

Postgres via Supabase · GitHub Actions to IONOS · MLS (RFC 9420) for
Freemarket · Stripe for subscriptions · Chuffed for crowdfunding, linked out

## Development

```bash
npm ci
cp .env.example .env     # beta credentials only; production is never local
npm run dev
```

Builds deploy to an admin-only beta for human review before reaching anyone
else. Nothing reaches production without that check.

## Contributing

Read [CONTRIBUTING.md](CONTRIBUTING.md) first. Contributions require a signed
[CLA](CLA.md) — this exists so stewardship can eventually pass to a non-profit
without tracking down every past contributor, and it explicitly forbids the
project ever being made proprietary.

## Security

Do not open a public issue for a vulnerability. See [SECURITY.md](SECURITY.md).

## Stewardship

Currently maintained by one person. The long-term intent is transfer to a
non-profit foundation, with surplus beyond salaries going to charitable
purposes. See MISSION.md.
