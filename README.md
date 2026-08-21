# Vsevolod Markov

Automation and applied AI, based in Barcelona.

I build internal systems that run without being watched. For the past year that has meant
being the only engineer on two production platforms at once — deciding the architecture,
deploying it, and being the person who gets called when it breaks.

## What I actually work on

**A tender-automation platform for a business-travel agency.** Public procurement notices
arrive continuously; a model reads and classifies them for relevance, pulls the full document
archive, and writes structured requirements into the CRM. One click then splits a bundled
procurement pack — Russian law puts 5–15 distinct forms inline in a single file, each of which
must be submitted separately — into standalone documents, fills them from a verified company
profile, and hands them back submission-ready. It took the team from roughly one or two
tenders a day to about ten.

**The part I find more interesting than the automation:** the output is a bid under public
procurement regulation, and it is binding once filed. So no price and no tender-specific value
is ever model-generated. Only profile-verified data is written, every filled pack lands in a
review state before a person submits it, and the fill logic fails blank rather than failing
wrong. Getting that right meant negative tests guarding the wrong-fill direction, per-shape
bindings so a template change cannot silently write into the wrong cell, and segmenting a
bundle before filling so each form fails in isolation instead of taking the pack down with it.

**Production safeguards that exist because something went wrong first:** a fail-closed spend
circuit-breaker built after a real cost leak, webhook de-duplication, retry and backoff against
an unreliable vendor API, and static eval checks wrapped around a non-deterministic core.

## Here

Most of what I have built is a client's and cannot be published. What is here is either
mine outright or rebuilt from scratch to be shareable.

- **[bank-transfers-tracker](https://github.com/Scorpez/bank-transfers-tracker)** — syncing personal finances
  across two banks with incompatible interfaces: one has a REST API, the other has no API at
  all and a CSV export whose column headers change with the account's locale. Small, tested,
  and honest about the awkward parts.

*More landing here as it is rebuilt clean — a retrieval-augmented notes server, and a
public-tender pipeline running against real procurement documents with a fictional company
profile.*

## Working with

Python · SQL and Postgres · TypeScript · n8n · Docker · LLM APIs · CRM platforms

## Elsewhere

- [LinkedIn](https://linkedin.com/in/vsevolod-markov)
- Barcelona, Spain — authorised to work in Spain, no sponsorship required
- Russian and English natively, Spanish at B2 and climbing
