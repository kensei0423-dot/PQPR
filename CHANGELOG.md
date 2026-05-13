# Changelog

All notable changes to this project will be documented in this file.

## [1.2.1] - 2026-05-13

### Added
- Error logging system with debug IDs and cloud screenshots
- SafeError — sanitize sensitive info from error messages
- Auto-fetch PayPal merchant ID on credential setup
- Sandbox/Live environment toggle
- ProGuard rules to strip logs in release builds

### Changed
- App name: "PayPal QR" → "PP QR"
- Live API endpoint: `api-m.paypal.com` → `api.paypal.com`
- `allowBackup` set to `false` for security

### Fixed
- CRYPTO_KEY_HEX length corrected (63 → 64 hex chars)
- Empty merchant_id UUID causing database insert failures

## [1.2.0] - 2026-05-09

### Added
- Buyer return page (success/cancel) with Node.js server
- Product management (quick-select items)
- Dashboard with revenue chart
- Pickup code system
- Order lookup by ID or pickup code
- Bluetooth receipt printer support
- Voice announcement on payment
- Admin PIN lock
- Feedback submission
- In-app update mechanism
- QR code logo customization

## [1.1.0] - 2026-05-05

### Added
- Transaction history with search and CSV export
- Full and partial refund support
- Multi-currency support
- Supabase Auth (email OTP login)
- Encrypted credential storage

## [1.0.0] - 2026-04-28

### Added
- Initial release
- PayPal QR code payment
- Fixed and free amount modes
- Basic transaction recording
