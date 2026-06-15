# Paymob (paymob)

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
