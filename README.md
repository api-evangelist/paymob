# Paymob (paymob)

Paymob is a Cairo-headquartered, licensed payment infrastructure provider for the MENAP region. Serving roughly 390,000 merchants across Egypt, Saudi Arabia, the United Arab Emirates, Oman, and Pakistan (with Qatar announced), Paymob unifies card acquiring, regional mobile wallets (Vodafone Cash, Etisalat Cash, Orange Money, STC Pay, Oman Net, EasyPaisa, JazzCash), BNPL rails (Tabby, Tamara, valU, Souhoola, Forsa, Aman), Apple Pay, Google Pay, POS terminals, subscriptions, installments, marketplace payouts, mass disbursement (Paymob Send), and an end-to-end cashless commerce platform (Paymob Sync) behind a single Accept / Intentions API surface.

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/paymob/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-paymob&utm_content=repo)

## Tags

- Payments, Payment Gateway, Fintech, MENA, MENAP, Egypt, Saudi Arabia, UAE, Pakistan, Oman, Card Payments, Mobile Wallets, BNPL, Payouts, Subscriptions

## Timestamps

- **Created:** 2026-05-24
- **Modified:** 2026-05-24

## Regions

| Country | Code | Currency | Base URL | Notable Payment Methods |
|---|---|---|---|---|
| Egypt | EG | EGP | https://accept.paymob.com | Cards, Vodafone Cash, Etisalat Cash, Orange Money, Aman, valU, Souhoola, Forsa, Meeza, Apple Pay |
| Saudi Arabia | SA | SAR | https://ksa.paymob.com | Mada, Cards, Apple Pay, Google Pay, STC Pay, Tabby, Tamara |
| United Arab Emirates | AE | AED | https://uae.paymob.com | Cards, Apple Pay, Google Pay, Tabby, Tamara |
| Oman | OM | OMR | https://oman.paymob.com | Cards, Oman Net |
| Pakistan | PK | PKR | https://pakistan.paymob.com | Cards, EasyPaisa, JazzCash |
| Qatar | QA | QAR | (announced) | TBD |

## APIs

### Paymob Intentions API
Modern v1 entry point. Backend creates an intention with the Secret Key and an array of `payment_methods`; Paymob returns a `client_secret` used to launch the Unified Checkout, render the Pixel component, or confirm headlessly.

**Human URL:** [https://developers.paymob.com/paymob-docs/developers/intention-apis/create-intention](https://developers.paymob.com/paymob-docs/developers/intention-apis/create-intention)

- [Documentation](https://developers.paymob.com/paymob-docs/developers/intention-apis/create-intention)
- [API Reference](https://docs.paymob.com/reference/next_v1_intentions_confirm_create)
- [OpenAPI](openapi/paymob-intentions-api-openapi.yml)
- [JSON Schema — Intention](json-schema/paymob-intention-schema.json)
- [Example — Create Intention](examples/paymob-create-intention-example.json)
- [Naftiko Capability — Intentions](capabilities/intentions-intentions.yaml)

### Paymob Accept API
Legacy v2 surface used by the standard redirect, iframe, MOTO, and headless flows. Provides auth, order registration, payment keys, capture/void/refund, transaction inquiry, and the V2 Quick Link payment-link API.

**Human URL:** [https://developers.paymob.com/paymob-docs/integration-paths/apis](https://developers.paymob.com/paymob-docs/integration-paths/apis)

- [Documentation](https://developers.paymob.com/paymob-docs/integration-paths/apis)
- [Standard Redirect](https://docs.paymob.com/docs/accept-standard-redirect)
- [OpenAPI](openapi/paymob-accept-api-openapi.yml)
- [JSON Schema — Transaction](json-schema/paymob-transaction-schema.json)
- [Example — Refund](examples/paymob-refund-transaction-example.json)
- [Naftiko Capability — Transactions](capabilities/accept-transactions.yaml)
- [Naftiko Capability — Payment Links](capabilities/accept-payment-links.yaml)

### Paymob Subscriptions API
Plan and subscription management with suspend/resume/cancel, retry windows, and secondary card attachment. Initial card capture flows through `/v1/intention/`.

- [OpenAPI](openapi/paymob-subscriptions-api-openapi.yml)
- [Naftiko Capability — Subscription Plans](capabilities/subscriptions-plans.yaml)

### Paymob Card Tokens API
Tokenisation surface for the "Pay with saved card" flow. Lists/deletes tokens and runs customer- and merchant-initiated transactions (CIT/MIT) for recurring, on-demand, and one-click payments.

- [OpenAPI](openapi/paymob-card-tokens-api-openapi.yml)
- [Naftiko Capability — Saved Cards](capabilities/card-tokens-saved-cards.yaml)

### Paymob Payouts (Send) API
Mass disbursement to mobile wallets (Vodafone Cash, Etisalat Cash, Orange Money), bank wallets, bank cards, and instant bank rails. OAuth2 password-grant authentication; instant cashin, bulk disbursement, budget inquiry, topup, and bulk transaction inquiry endpoints.

**Human URL:** [https://payouts.paymobsolutions.com/docs/](https://payouts.paymobsolutions.com/docs/)

- [Documentation](https://payouts.paymobsolutions.com/docs/)
- [Swagger UI](https://payouts.paymobsolutions.com/docs/swagger-ui/)
- [Authentication](https://payouts.paymobsolutions.com/docs/generate_and_refresh_token_api/)
- [OpenAPI](openapi/paymob-payouts-api-openapi.yml)
- [JSON Schema — Disbursement](json-schema/paymob-disbursement-schema.json)
- [Example — Instant Cashin](examples/paymob-instant-cashin-example.json)
- [Naftiko Capability — Disbursement](capabilities/payouts-disbursement.yaml)

## Pricing (summary)

| Plan | Country | Per Transaction | Notes |
|---|---|---|---|
| Standard | Egypt | 2.75% + 3 EGP | No monthly fees; weekly settlement |
| Standard | UAE | 2.9% + 1 AED (local & international) | Optional 210 AED/month daily-settlement add-on |
| Enterprise | All | Custom MDR | Volume-based; dedicated team; multi-region settlement |

Detailed structured pricing: [plans/paymob-plans-pricing.yml](plans/paymob-plans-pricing.yml)

## Rate Limits

- Accept v2 `auth_token` TTL: **60 minutes**
- Payouts `access_token` TTL: **60 minutes** (use `refresh_token` to rotate)
- Intentions `client_secret` expiration: **3600 seconds** (configurable)
- Production transaction velocity quotas are negotiated per merchant agreement.

See [rate-limits/paymob-rate-limits.yml](rate-limits/paymob-rate-limits.yml) and the FinOps profile at [finops/paymob-finops.yml](finops/paymob-finops.yml).

## SDKs

| Language | Repository |
|---|---|
| Node.js | [paymob-node](https://github.com/PaymobAccept/paymob-node) |
| PHP | [paymob-php](https://github.com/PaymobAccept/paymob-php) |
| Python | [paymob-python](https://github.com/PaymobAccept/paymob-python) |
| Java | [paymob-java](https://github.com/PaymobAccept/paymob-java) |
| JavaScript (Flash Checkout) | [paymob-js](https://github.com/PaymobAccept/paymob-js) |
| Flutter | [flutter_sdk](https://github.com/PaymobAccept/flutter_sdk) |
| React Native | [paymob-reactnative-sdk](https://github.com/PaymobAccept/paymob-reactnative-sdk) |
| Android | [Android-SDK](https://github.com/PaymobAccept/Android-SDK) |
| iOS (Swift) | [Swift-iOS](https://github.com/PaymobAccept/Swift-iOS) |
| WooCommerce | [accept-woocommerce](https://github.com/PaymobAccept/accept-woocommerce) |
| Magento 2 | [accept-magento2](https://github.com/PaymobAccept/accept-magento2) |
| OpenCart | [accept-opencart](https://github.com/PaymobAccept/accept-opencart) |
| Postman | [API-Postman-Collections](https://github.com/PaymobAccept/API-Postman-Collections) |
| Claude Skill | [Paymob-Claude-Integration-Skill](https://github.com/PaymobAccept/Paymob-Claude-Integration-Skill) |

## Common Links

- [Paymob Developer Portal](https://developers.paymob.com)
- [Paymob Documentation Hub](https://developers.paymob.com/paymob-docs)
- [Paymob Egypt Hub](https://developers.paymob.com/hub/egypt)
- [Paymob KSA Hub](https://developers.paymob.com/hub/sa)
- [Paymob UAE](https://paymob.ae)
- [API Reference (Theneo)](https://docs.paymob.com)
- [Accept Merchant Dashboard](https://accept.paymob.com/portal2/en/login)
- [Pricing — Egypt](https://www.paymob.com/en/pricing) · [Pricing — UAE](https://paymob.ae/en/pricing)
- [GitHub Organization](https://github.com/PaymobAccept)
- [LinkedIn](https://www.linkedin.com/company/paymobcompany)
- [Terms of Service](https://paymob.com/en/terms-conditions) · [Privacy Policy](https://paymob.com/en/privacy-policy)

## Artifacts

- [apis.yml](apis.yml) — APIs.json catalog entry
- [openapi/](openapi/) — OpenAPI 3.0 specifications (5 files)
- [capabilities/](capabilities/) — Naftiko capability definitions (6 files)
- [json-schema/](json-schema/) — JSON Schema for Intention, Transaction, Disbursement
- [json-ld/paymob-context.jsonld](json-ld/paymob-context.jsonld) — JSON-LD context
- [examples/](examples/) — Request/response examples
- [plans/paymob-plans-pricing.yml](plans/paymob-plans-pricing.yml) — API Commons Plans 0.1
- [rate-limits/paymob-rate-limits.yml](rate-limits/paymob-rate-limits.yml) — API Commons Rate Limits 0.1
- [finops/paymob-finops.yml](finops/paymob-finops.yml) — FOCUS-aligned FinOps definition
- [rules/paymob-rules.yml](rules/paymob-rules.yml) — Spectral ruleset
- [vocabulary/paymob-vocabulary.yml](vocabulary/paymob-vocabulary.yml) — Controlled vocabulary
