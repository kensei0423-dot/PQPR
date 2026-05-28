# PP QR

A merchant-side Android app for accepting payments via QR code, powered by PayPal Orders API v2.

Customers scan the QR code with their phone, pay through PayPal, and the merchant gets instant confirmation with receipt printing and voice announcement support.

[![Download APK](https://img.shields.io/badge/Download-APK-green?style=for-the-badge&logo=android)](https://github.com/kensei0423-dot/PQPR/releases/latest)

## Features

- **QR Code Payment** — Generate dynamic QR codes for each transaction
- **Fixed & Free Amount** — Support both preset and custom payment amounts
- **Multi-Currency** — USD, EUR, GBP, JPY, TWD, and more
- **Transaction History** — View, search, and export past transactions (CSV)
- **Refund** — Full and partial refunds directly from the app
- **Receipt Printing** — Bluetooth thermal printer support (ESC/POS)
- **Voice Announcement** — Audio confirmation on successful payment
- **Dashboard** — Daily/weekly/monthly revenue stats with bar chart
- **Pickup Code** — Auto-generated pickup codes for order fulfillment
- **Order Lookup** — Search transactions by order ID or pickup code
- **Error Logging** — Automatic error capture with debug IDs and screenshots to cloud
- **Auto Update** — In-app update mechanism with version control
- **BOPIS** — Buy Online, Pickup In-Store with PayPal Seller Protection (`PICKUP_IN_STORE`)
- **Multi-Store Management** — Add and manage multiple pickup locations with address details
- **Security** — Encrypted local storage (AES-256), Supabase RLS per-merchant isolation, credential encryption, ProGuard obfuscation

## Tech Stack

- **Platform**: Android (API 26+)
- **Language**: Kotlin
- **UI**: Jetpack Compose, Material 3
- **Backend**: Supabase (Auth, Database, Storage)
- **Payment**: PayPal Orders API v2
- **Security**: Hardware-backed encrypted storage, AES-256 encryption
- **Connectivity**: Bluetooth printing, QR code generation

## Security

- Credentials encrypted at rest on device and in cloud
- Sensitive data stripped from all user-facing error messages
- Debug logging disabled in production builds
- Local backup disabled to prevent data extraction
- Code obfuscation enabled for release builds

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

## Disclaimer

This app is an independent third-party tool. It is not affiliated with, endorsed by, or sponsored by PayPal, Inc. PayPal is a registered trademark of PayPal, Inc.
