# Mission

Haymarket Social is an organizing platform. It exists so that people can find
each other, decide things together, and hold institutions accountable — and
so that doing those things does not create a record that can be used against
them.

The name references the Haymarket affair of 1886, and the eight-hour day that
came out of the organizing around it.

## What this platform is for

Organizing is not posting. The tools that dominate social media are built to
maximize attention, because attention is what they sell. That business model
shapes everything downstream of it: what gets amplified, what gets collected,
who the customer actually is. A platform for organizing has to be built on a
different foundation, because the thing it is optimizing for is different.

Haymarket is built for the parts of organizing that are unglamorous and
load-bearing. Finding the other people at your workplace. Getting twelve
people to a meeting. Keeping a campaign pointed at an institution over
months. Remembering what was decided.

## What we will not do

These are commitments, not preferences. They are enforced in the codebase
and documented in CHARTER.md, and they are the reason the code is public
under a license that requires it to stay public.

**We do not monetize members or their data.** No behavioral advertising, no
programmatic ad tech, no selling or licensing or brokering member data in any
form, including aggregate or de-identified. Revenue comes from organizations
with budgets — subscriptions, group capacity, verified profiles, a job board,
flat-rate first-party sponsorships. If the only way to fund something is to
monetize the people using it, we do not build that thing.

**We do not collect what we do not need.** Membership on this platform
reveals political affiliation. That makes every stored row something that
could be subpoenaed, breached, scraped, or used to target someone for
harassment or retaliation at work. So: no phone numbers, no precise location
on a person's record, no read receipts, no presence tracking, no message
search on the server, no sender recorded on encrypted messages. Retention is
short and enforced by a job that actually runs.

But privacy that breaks the product protects nobody, because nobody uses it.
Where a feature needs data to work, it gets what it needs, scoped tightly,
held briefly, and disclosed plainly.

**We do not make this a tool for targeting people.** Campaign and boycott
targets are constrained at the database level to institutions. This is
enforced in the schema rather than in a policy document, because policy
documents are not enforcement.

**We do not overstate what we protect.** Freemarket, the encrypted messaging
client, is end-to-end encrypted, and it also runs in a browser, which means a
compromised or compelled server could serve modified code. We say so on a
public limitations page rather than burying it. For situations where that
threat is real, use Signal. We would rather lose a user to a better tool than
keep one on a false promise.

**We disclose every third party.** Every external service the platform
depends on is listed publicly at /services with what goes to it, what comes
back, and why — and carries visible attribution on the surface that uses it.

## Long-term stewardship

The founder's intent is that Haymarket Social eventually passes to a
non-profit foundation, and that the platform's surplus, after paying the
people who do the work, goes to charitable purposes. That transfer is
planned for the distant future and nothing about it is binding today.

The reason to write it down now is that intent is the thing most likely to be
lost. Code survives. Infrastructure survives. What a project was *for* tends
to erode quietly, one reasonable-seeming decision at a time — and the
pressure to erode it is always strongest when the platform is doing well
enough to be worth compromising.

This file is the record of what it was for.

## To anyone who forks this

The license requires you to keep your modified source open and offered to
your users. That requirement is deliberate: the guarantees above are only
verifiable if the code is readable.

You are free to run this, change it, and disagree with everything here. What
you cannot do is run a modified version whose privacy guarantees are weaker
than the ones described, while keeping the source closed, under this name.
The license handles the source. The trademark handles the name.
