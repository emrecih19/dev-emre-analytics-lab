# Quality Assurance Summary

## Validation Environment

- WordPress and WooCommerce staging environment
- Google Tag Manager Preview Mode
- Google Tag Assistant
- GA4 DebugView
- Chrome Developer Tools
- CookieYes Consent Management Platform

## Consent Mode v2 Validation

The following Consent Mode v2 signals were validated:

- analytics_storage
- ad_storage
- ad_user_data
- ad_personalization

### Expected Default State

All four signals are initialized as denied before user interaction.

### Expected Opt-In State

After explicit user consent, the relevant consent signals update to granted.

### Additional Controls

- Ads Data Redaction enabled
- URL Passthrough enabled
- Consent preferences persist across subsequent page navigation

## Ecommerce Validation

The following interactions were tested:

- Product view
- Add-to-cart interaction on product listings
- Add-to-cart interaction on individual product pages
- Checkout initiation
- Purchase completion

Purchase validation included:

- Transaction ID
- Revenue
- Currency
- Item array
- Product identifiers
- Quantity
- Tag firing behavior

## Error Tracking Validation

The page_not_found event was tested using an intentionally invalid URL.

The event includes:

- page_location
- page_referrer

## Known Limitation

The DOM-based add-to-cart fallback measures user intent rather than a confirmed backend cart mutation.

A future implementation would dispatch the event only after a successful WooCommerce AJAX response or confirmed cart update.