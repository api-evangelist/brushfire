# Brushfire (brushfire)

Brushfire is an event ticketing, registration, and virtual event platform used by churches, ministries, conferences, attractions, and large events. Alongside its hosted box office, embeddable event widgets, reserved seating, and mobile check-in apps, Brushfire publishes a documented REST API at `api.brushfire.com` for building custom integrations - synchronizing data with other systems, reserving attendees, and processing transactions.

The API is a real, public OpenAPI 3.0.1 surface (118 paths / 135 operations) served from the Swagger UI at [api.brushfire.com/swagger](https://api.brushfire.com/swagger/index.html). It is authenticated with an **App Key** sent in the `Authorization` header (requested free at [developer.brushfire.com/key](https://developer.brushfire.com/key)) and is **date-versioned**: send the desired version in an `api-version` request header (for example `2025-07-22`). A missing version returns `412 Precondition Failed`. Rate limiting is enforced with `429 Too Many Requests` and `X-Rate-Limit-Limit` / `X-Rate-Limit-Remaining` / `X-Rate-Limit-Reset` response headers.

**Access model:** Brushfire is a closed-source commercial SaaS. The OpenAPI document is publicly readable, but calling the endpoints requires a Brushfire account and an App Key. The endpoints documented here are taken verbatim from Brushfire's published OpenAPI document; request/response bodies were not exercised live because they require authentication. Pricing is a per-ticket fee (varying by organization type) plus Stripe/Square card processing - the API itself carries no separate fee.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/brushfire/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/brushfire/refs/heads/main/apis.yml)

## Tags

- Event Ticketing
- Registration
- Events
- Ticketing
- Check-In
- Churches
- Payments

## Timestamps

- **Created:** 2026-07-05
- **Modified:** 2026-07-05

## APIs

### Brushfire Events API

List, create, retrieve, archive, and restore events, and read their nested resources - ticket types, sections, seats, best-available seating, sessions, fields and field metadata, documents, groups, orders, payment methods, theme, and reports. The core catalog surface for an event's inventory and configuration.

- **Human URL:** [https://developer.brushfire.com](https://developer.brushfire.com)
- **Base URL:** `https://api.brushfire.com`

#### Tags

- Events
- Types
- Sections
- Seats

#### Properties

- [Documentation](https://developer.brushfire.com)
- [API Reference](https://api.brushfire.com/swagger/index.html)
- [OpenAPI](openapi/brushfire-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Brushfire Attendees API

Retrieve and manage individual attendees - read and update buyer and attendee fields (standard and custom), cancel, reassign ticket type, move between groups and communities, gift or link tickets, record donations, generate access codes, and print or batch-print tickets and badges.

- **Human URL:** [https://developer.brushfire.com](https://developer.brushfire.com)
- **Base URL:** `https://api.brushfire.com`

#### Tags

- Attendees
- Registration
- Check-In

#### Properties

- [Documentation](https://developer.brushfire.com)
- [API Reference](https://api.brushfire.com/swagger/index.html)
- [OpenAPI](openapi/brushfire-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Brushfire Orders API

List and retrieve orders, read and update order fields, resend confirmations, and create orders through multiple transaction paths - standard checkout, direct orders, point-of-sale (POS), card-reader (terminal) sales, and SMS orders. Carries Brushfire's order and payment transaction processing.

- **Human URL:** [https://developer.brushfire.com](https://developer.brushfire.com)
- **Base URL:** `https://api.brushfire.com`

#### Tags

- Orders
- Transactions
- Point of Sale

#### Properties

- [Documentation](https://developer.brushfire.com)
- [API Reference](https://api.brushfire.com/swagger/index.html)
- [OpenAPI](openapi/brushfire-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Brushfire Cart & Checkout API

Build and manage a shopping cart across events and attendees - add and remove events, reserve and configure attendees, complete registration forms, apply and remove promotions, and look up cart state prior to converting a cart into a paid order.

- **Human URL:** [https://developer.brushfire.com](https://developer.brushfire.com)
- **Base URL:** `https://api.brushfire.com`

#### Tags

- Cart
- Checkout
- Transactions

#### Properties

- [Documentation](https://developer.brushfire.com)
- [API Reference](https://api.brushfire.com/swagger/index.html)
- [OpenAPI](openapi/brushfire-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Brushfire Sessions & Check-In API

Drive on-site attendance for a session - list session attendees, look up by email, check attendees in and out, and run flexible (flex) check-in and checkout for groups and individual attendees, orders, and groups within a session.

- **Human URL:** [https://developer.brushfire.com](https://developer.brushfire.com)
- **Base URL:** `https://api.brushfire.com`

#### Tags

- Sessions
- Check-In
- Attendance

#### Properties

- [Documentation](https://developer.brushfire.com)
- [API Reference](https://api.brushfire.com/swagger/index.html)
- [OpenAPI](openapi/brushfire-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Brushfire Groups API

Create and update groups, read and write group fields, assign a group to a community, and print or batch-print the tickets and badges for everyone in a group - the container for family, team, and organization registrations.

- **Human URL:** [https://developer.brushfire.com](https://developer.brushfire.com)
- **Base URL:** `https://api.brushfire.com`

#### Tags

- Groups
- Communities
- Registration

#### Properties

- [Documentation](https://developer.brushfire.com)
- [API Reference](https://api.brushfire.com/swagger/index.html)
- [OpenAPI](openapi/brushfire-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Brushfire Promotions & Access Codes API

List and retrieve promotions and access codes, bulk-import promotions, and generate dynamic promotions and access codes - the discounting and gated-access controls layered onto an event's ticket types and sections.

- **Human URL:** [https://developer.brushfire.com](https://developer.brushfire.com)
- **Base URL:** `https://api.brushfire.com`

#### Tags

- Promotions
- Access Codes
- Discounts

#### Properties

- [Documentation](https://developer.brushfire.com)
- [API Reference](https://api.brushfire.com/swagger/index.html)
- [OpenAPI](openapi/brushfire-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Brushfire Webhooks (Hooks) API

Subscribe and unsubscribe HTTP webhook endpoints, update subscriptions, list active hooks, send test pings and sample payloads, and poll for events - Brushfire's outbound event-notification surface delivered as HTTP callbacks, not a WebSocket stream.

- **Human URL:** [https://developer.brushfire.com](https://developer.brushfire.com)
- **Base URL:** `https://api.brushfire.com`

#### Tags

- Webhooks
- Hooks
- Events

#### Properties

- [Documentation](https://developer.brushfire.com)
- [API Reference](https://api.brushfire.com/swagger/index.html)
- [OpenAPI](openapi/brushfire-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/brushfire-technology)
- [Website](https://www.brushfire.com)
- [Documentation](https://developer.brushfire.com)
- [API Reference](https://api.brushfire.com/swagger/index.html)
- [Sign Up (App Key)](https://developer.brushfire.com/key)
- [Plans](plans/brushfire-plans-pricing.yml)
- [Rate Limits](rate-limits/brushfire-rate-limits.yml)
- [Fin Ops](finops/brushfire-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
