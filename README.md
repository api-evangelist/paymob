# Paymob (paymob)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Paymob is a Cairo-headquartered, licensed payment infrastructure provider for the MENAP region. Serving roughly 390,000 merchants across Egypt, Saudi Arabia, the United Arab Emirates, Oman, and Pakistan (with Qatar announced), Paymob unifies card acquiring, regional mobile wallets (Vodafone Cash, Etisalat Cash, Orange Money, STC Pay, Oman Net, EasyPaisa, JazzCash), BNPL rails (Tabby, Tamara, valU, Souhoola, Forsa, Aman), Apple Pay, Google Pay, POS terminals, subscriptions, installments, marketplace payouts, mass disbursement (Paymob Send), and an end-to-end cashless commerce platform (Paymob Sync) behind a single Accept / Intentions API surface.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/paymob/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/paymob/refs/heads/main/apis.yml)

## Scope

- **Position:** Consuming
- **Access:** 3rd-Party

## Tags

- Payments
- Payment Gateway
- Fintech
- MENA
- MENAP
- Egypt
- Saudi Arabia
- UAE
- Pakistan
- Oman
- Card Payments
- Mobile Wallets
- BNPL
- Payouts
- Subscriptions

## Timestamps

- **Created:** 2026-05-24
- **Modified:** 2026-05-24

## APIs

### Paymob Intentions API

The v1 Intentions API is Paymob's modern entry point for payment acceptance. The merchant backend creates an intention with the secret key and an array of payment_methods (integration IDs or named methods like apple_pay, tabby, tamara, stc_pay, easypaisa, jazzcash). Paymob returns a client_secret used to launch the Unified Checkout, render the Pixel component, or confirm the payment headlessly.

- **Human URL:** [https://developers.paymob.com/paymob-docs/developers/intention-apis/create-intention](https://developers.paymob.com/paymob-docs/developers/intention-apis/create-intention)

#### Tags

- Payments
- Intentions
- Checkout
- MENA

#### Properties

- [Documentation](https://developers.paymob.com/paymob-docs/developers/intention-apis/create-intention)
- [API Reference](https://docs.paymob.com/reference/next_v1_intentions_confirm_create)
- [OpenAPI](openapi/paymob-intentions-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/paymob-intentions-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/paymob-intentions-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/paymob-intention-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/paymob-create-intention-example.json)

### Paymob Accept API

The legacy v2 Accept API uses the three-step authentication-order-payment key flow plus operations for capture, void, refund, transaction inquiry by id or merchant order id, and the V2 Quick Link API for sharable payment links. Still actively used by merchants on the standard redirect, iframe, and headless MOTO integrations.

- **Human URL:** [https://developers.paymob.com/paymob-docs/integration-paths/apis](https://developers.paymob.com/paymob-docs/integration-paths/apis)

#### Tags

- Payments
- Accept
- Transactions
- MENA

#### Properties

- [Documentation](https://developers.paymob.com/paymob-docs/integration-paths/apis)
- [Documentation](https://docs.paymob.com/docs/accept-standard-redirect)
- [OpenAPI](openapi/paymob-accept-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/paymob-accept-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/paymob-accept-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/paymob-transaction-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/paymob-refund-transaction-example.json)

### Paymob Subscriptions API

The Subscriptions Module manages subscription plans (create, list, update, suspend, resume) and per-customer subscriptions billed against tokenised cards. Lifecycle operations cover suspend, resume, cancel, secondary card attachment, and transaction inspection. Initial subscription creation flows through /v1/intention/ for card capture.

- **Human URL:** [https://developers.paymob.com](https://developers.paymob.com)

#### Tags

- Payments
- Subscriptions
- Recurring Billing

#### Properties

- [Documentation](https://developers.paymob.com)
- [OpenAPI](openapi/paymob-subscriptions-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/paymob-subscriptions-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/paymob-subscriptions-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Paymob Card Tokens API

Tokenisation surface for the Paymob "Pay with saved card" flow. Lists and deletes tokenised cards and runs both customer-initiated (CIT) and merchant-initiated (MIT) transactions against saved tokens for recurring, on-demand, and one-click payments.

- **Human URL:** [https://developers.paymob.com](https://developers.paymob.com)

#### Tags

- Payments
- Card Tokens
- Saved Cards
- CIT
- MIT

#### Properties

- [Documentation](https://developers.paymob.com)
- [OpenAPI](openapi/paymob-card-tokens-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/paymob-card-tokens-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/paymob-card-tokens-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Paymob Payouts (Send) API

Paymob Send is the mass-payout product used to disburse funds to suppliers, employees, gig workers, and consumers via mobile wallets (Vodafone Cash, Etisalat Cash, Orange Money), bank wallets, bank cards, and instant bank rails. OAuth2 password-grant authentication; supports instant cashin, bulk disbursement, budget inquiry, topup request/inquiry, and bulk transaction inquiry by id or reference.

- **Human URL:** [https://payouts.paymobsolutions.com/docs/](https://payouts.paymobsolutions.com/docs/)

#### Tags

- Payouts
- Disbursement
- Mass Payments
- MENA

#### Properties

- [Documentation](https://payouts.paymobsolutions.com/docs/)
- [API Reference](https://payouts.paymobsolutions.com/docs/swagger-ui/)
- [Authentication](https://payouts.paymobsolutions.com/docs/generate_and_refresh_token_api/)
- [OpenAPI](openapi/paymob-payouts-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/paymob-payouts-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/paymob-payouts-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/paymob-disbursement-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/paymob-instant-cashin-example.json)

## Common Properties

- [Portal](https://paymob.com)
- [Developer Portal](https://developers.paymob.com)
- [Documentation](https://developers.paymob.com/paymob-docs)
- [Getting Started](https://developers.paymob.com/paymob-docs/getting-started/overview)
- [Hub](https://developers.paymob.com/hub/egypt)
- [Hub](https://developers.paymob.com/hub/sa)
- [Hub](https://paymob.ae)
- [API Reference](https://docs.paymob.com)
- [Console](https://accept.paymob.com/portal2/en/login)
- [Sign Up](https://accept.paymob.com/portal2/en/register)
- [Pricing](https://www.paymob.com/en/pricing)
- [Pricing](https://paymob.ae/en/pricing)
- [Plans](plans/paymob-plans-pricing.yml)
- [Rate Limits](rate-limits/paymob-rate-limits.yml)
- [Documentation](finops/paymob-finops.yml)
- [Documentation](rules/paymob-rules.yml)
- [Documentation](vocabulary/paymob-vocabulary.yml)
- [JSON-LD](json-ld/paymob-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [GitHub Organization](https://github.com/PaymobAccept)
- [SDK](https://github.com/PaymobAccept/paymob-node)
- [SDK](https://github.com/PaymobAccept/paymob-php)
- [SDK](https://github.com/PaymobAccept/paymob-python)
- [SDK](https://github.com/PaymobAccept/paymob-java)
- [SDK](https://github.com/PaymobAccept/paymob-js)
- [SDK](https://github.com/PaymobAccept/flutter_sdk)
- [SDK](https://github.com/PaymobAccept/paymob-reactnative-sdk)
- [SDK](https://github.com/PaymobAccept/Android-SDK)
- [SDK](https://github.com/PaymobAccept/Swift-iOS)
- [SDK](https://github.com/PaymobAccept/accept-woocommerce)
- [SDK](https://github.com/PaymobAccept/accept-magento2)
- [SDK](https://github.com/PaymobAccept/accept-opencart)
- [Documentation](https://github.com/PaymobAccept/API-Postman-Collections)
- [SDK](https://github.com/PaymobAccept/Paymob-Claude-Integration-Skill)
- [LinkedIn](https://www.linkedin.com/company/paymobcompany)
- [Portal](https://paymob.com/en/about-us)
- [Contact](https://paymob.com/en/contact-us)
- [Terms of Service](https://paymob.com/en/terms-conditions)
- [Privacy Policy](https://paymob.com/en/privacy-policy)
- [Features](undefined)
- [Use Cases](undefined)
- [Integrations](undefined)
- [Solutions](undefined)
- [Plans](plans/paymob-plans-pricing.yml)
- [Rate Limits](rate-limits/paymob-rate-limits.yml)
- [Documentation](finops/paymob-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
**URL:** https://apievangelist.com
