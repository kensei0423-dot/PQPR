# Changelog

All notable changes to this project will be documented in this file.

## [1.3.0] - 2026-05-28

### Added
- **BOPIS (Buy Online, Pickup In-Store)** — Full integration with PayPal `PICKUP_IN_STORE` shipping type and `SET_PROVIDED_ADDRESS` preference for Seller Protection
- **Multi-store management** — Add, edit, delete multiple pickup store locations in Settings; dropdown selector with address detail card
- **Supabase RLS (Row Level Security)** — Per-merchant data isolation; each user only sees their own transactions and credentials
- **JWT auto-refresh** — `alwaysAutoRefresh` + `autoLoadFromStorage` prevent silent auth failures after 1-hour token expiry
- **QR pending navigation guard** — Confirmation dialog when leaving payment screen with an active QR order (History, Settings, Cancel)
- **USER_GUIDE.md** — Comprehensive feature guide covering all 12 modules

### Changed
- **Products moved to local storage** — Product list stored in encrypted local prefs instead of Supabase; cleared on logout/re-auth
- **Merchant Name consolidated into Store Name** — Removed separate Merchant Name field; store name used across app as display name
- **Settings reorganization** — Store Locations below Authorization; Lookup & Refund and QR Logo merged into Business Tools section
- **saveTransaction now includes auth_user_id** — Required for RLS per-merchant isolation

### Fixed
- Navigation to History/Settings while QR payment pending no longer silently abandons orders
- Duplicate var declarations in PaymentScreen resolved

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
