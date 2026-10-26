# GOV.UK Notify

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

GOV.UK Notify is a UK government notification service operated by the Government Digital Service (GDS) that enables central government, local authorities, NHS organisations, and other eligible public bodies to send emails, text messages, and letters to citizens on behalf of government services.

## Overview

The platform currently serves 1,751 organisations across 12,296 services. It is designed so that non-technical users can create and manage notification templates through a web interface, while developers integrate sending and status-tracking programmatically via a REST API or official client libraries.

## Channels

- **Email** - Free and unlimited for all eligible organisations
- **SMS** - Annual free allowance by organisation type; 2.4p per message (plus VAT) above the allowance
- **Letters** - Priced by postage class and page count; includes double-sided colour print, C5 envelope, and postage

## API

The GOV.UK Notify REST API base URL is `https://api.notifications.service.gov.uk`. Authentication uses JSON Web Tokens (JWT) issued from API keys obtained in the GOV.UK Notify service dashboard. Tokens expire within 30 seconds.

### Core Endpoints

| Method | Path | Purpose |
|--------|------|---------|
| POST | /v2/notifications/email | Send an email |
| POST | /v2/notifications/sms | Send a text message |
| POST | /v2/notifications/letter | Send a letter |
| GET | /v2/notifications/{id} | Get notification status |
| GET | /v2/notifications | List notifications (up to 250 per page) |
| GET | /v2/notifications/{id}/pdf | Get letter PDF |
| GET | /v2/template/{id} | Get a template |
| GET | /v2/templates | List all templates |
| POST | /v2/template/{id}/preview | Preview a template |
| GET | /v2/received-text-messages | List received SMS |

### Rate Limits

- 3,000 messages per minute per API key type
- 250,000 emails per day
- 250,000 SMS per day
- 20,000 letters per day

## Client Libraries

Official clients are available for Python, Java, .NET, Node.js, PHP, and Ruby. All are maintained by the Government Digital Service under the alphagov GitHub organisation.

## Pricing

| Channel | Cost |
|---------|------|
| Email | Free (unlimited) |
| SMS (central gov) | 20,000 free/year; 2.4p each above |
| SMS (local authority) | 10,000 free/year; 2.4p each above |
| SMS (schools/other) | 5,000 free/year; 2.4p each above |
| Letter (economy, 1 sheet) | 64p |
| Letter (2nd class, 1 sheet) | 73p |
| Letter (1st class, 1 sheet) | £1.56 |
| Letter (international, 1 sheet) | £1.80 |

All prices exclude VAT. No monthly fees, no setup costs, no procurement requirements.

## Links

- Website: https://www.notifications.service.gov.uk/
- Documentation: https://docs.notifications.service.gov.uk/
- Pricing: https://www.notifications.service.gov.uk/pricing
- Status: https://status.notifications.service.gov.uk/
- Support: https://www.notifications.service.gov.uk/support
- Blog: https://gds.blog.gov.uk/category/gov-uk-notify/
- GitHub (API): https://github.com/alphagov/notifications-api
