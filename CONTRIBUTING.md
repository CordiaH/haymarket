# Contributing

Thanks for looking. A few things about this project make contributing here
different from most repos, so read this before opening a PR.

## The CLA

Every contribution needs a signed [CLA](CLA.md). Sign once; it covers all
future contributions.

The reason is narrower than most CLAs. The long-term intent is that this
project passes to a non-profit foundation, and you cannot transfer copyright
you do not hold. Without a CLA, the project's copyright ends up held in
scattered pieces by everyone who ever contributed, and the transfer either
becomes a years-long paperwork exercise or does not happen.

Section 9 is the part worth reading: it explicitly prevents the project from
ever being made proprietary. Your contributions cannot be used that way, by
anyone, including a future steward.

To sign: open a PR adding your name to `CONTRIBUTORS.md` with the statement
from CLA.md.

## Read the charter first

[CHARTER.md](CHARTER.md) contains thirteen rules that are settled decisions
rather than open questions. A PR that touches one will be closed regardless
of how good the code is. They exist because the platform holds data that
reveals political affiliation, and each of them fails catastrophically and
irreversibly if broken.

The ones contributors most often trip over:

- **No third-party JavaScript on any page.** This includes font CDNs,
  "privacy-friendly" analytics, and embeds. First-party or not at all.
- **RLS policy in the same migration that creates a table.** A table without
  a policy is a breach with a delay.
- **Every migration reversible.**
- **No logging of member identifiers, post content, IP addresses, or user
  agents.** If you need diagnostics, count things.
- **No sender column on `fm_messages`, ever.** The server not knowing is the
  design.

Several things in the schema look like omissions and are deliberate — no
presence table, no read receipts, no server-side search. If something seems
conspicuously missing, it was removed on purpose. Ask before adding it back.

## What gets merged easily

Bug fixes with a test. Accessibility improvements. Documentation. Anything
that deletes code without changing behavior. Performance work with a
measurement.

## What needs discussion first

Open an issue before writing code for: new dependencies, schema changes, new
data collected about members, anything touching auth, anything touching
Freemarket's cryptographic layer.

**Freemarket's MLS integration is human-written and human-reviewed.** No
generated cryptographic plumbing, no clever refactors of the key handling.
This is the one area where "it's simpler this way" is not sufficient
justification.

## New dependencies

Assume the answer is no for anything that makes network calls. In your PR,
name the package, its transitive weight, and what it does at runtime. Prefer
writing forty lines over adding a package. This codebase is maintained by one
person and every dependency is a standing obligation.

## Pull requests

Include:

- What changed and why, two sentences
- Schema changes listed explicitly, with the RLS policy quoted
- New member data collected, or "none"
- New dependencies, or "none"
- What you tested and what you did not
- What you are unsure about

The last line is not a formality. It is read first.

## Review

Some review on this project is automated, and automated reviewers can be
wrong in confident-sounding ways. Push back if a review comment is wrong — a
human reads the thread before anything merges.

Builds deploy to an admin-only beta and are reviewed by a human before
reaching any member. Merged is not shipped.

## Code of conduct

Behave like someone who wants this project to exist in ten years. Harassment,
bad-faith argument, and attempts to relitigate settled charter decisions will
get you shown the door. Disagreement is welcome; wearing people down is not.

## Contact

Security issues: see [SECURITY.md](SECURITY.md). Do not use the issue tracker.
