# Privacy Policy

**PP QR** — Last updated: May 2026

## Data We Collect

| Data | Purpose | Storage |
|------|---------|---------|
| Email address | Account authentication (OTP login) | Supabase Auth |
| PayPal API credentials | Payment processing | Encrypted on device only (secrets never leave the device) |
| Transaction records | Order history and refunds | Supabase PostgreSQL |
| Device model & OS version | Error diagnostics | Supabase PostgreSQL |
| App screenshots (on error only) | Debugging | Supabase Storage |

## Data We Do NOT Collect

- Location data
- Contacts
- Photos or media
- Browsing history
- Personal financial information (bank accounts, card numbers)

## How We Use Your Data

- **Authentication**: Email is used solely for OTP-based login via Supabase Auth.
- **Payment Processing**: PayPal credentials are used to create and capture orders through PayPal's API. We do not store buyer payment information.
- **Error Diagnostics**: When an error occurs, a screenshot of the app screen and device info may be captured automatically and uploaded to help diagnose issues. No personal data is intentionally included in screenshots.
- **Transaction History**: Payment records are stored to provide order management, refund processing, and revenue reporting features.

## Third-Party Services

This app integrates with the following third-party services:

- **PayPal** ([Privacy Policy](https://www.paypal.com/us/legalhub/privacy-full)) — Payment processing
- **Supabase** ([Privacy Policy](https://supabase.com/privacy)) — Authentication, database, and file storage

## Data Security

- API secrets stored only on device, never uploaded to cloud
- Local storage uses Android EncryptedSharedPreferences with hardware-backed keystore
- Release builds strip all debug logging

## Data Retention

- Account data is retained while your account is active
- Transaction records are retained for business reporting purposes
- Error logs are retained for diagnostic purposes and may be periodically purged

## Your Rights

You may request to:
- Access your stored data
- Delete your account and associated data
- Export your transaction history

## Contact

For privacy concerns, please open an issue on the [GitHub repository](https://github.com/kensei0423-dot/PQPR/issues).

## Changes

We may update this Privacy Policy from time to time. Changes will be posted in this file with an updated date.
