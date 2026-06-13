# GOV.UK Notify

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
