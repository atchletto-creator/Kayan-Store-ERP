# KAYAN STORE ERP — Known Limitations and Risks

This document tracks technical limitations and risks.
A feature must not be described as complete until it has been tested.

## 1. Offline Storage
- Browser storage is not guaranteed to be permanent.
- Users may lose local unsynchronized data if browser storage is cleared or the device is lost.
- Request persistent storage where supported.
- Display warnings for pending and old unsynchronized operations.
- Local storage is not a backup.
- Test synchronization after reconnecting.

## 2. Offline Sales Conflicts
- Two devices may attempt to sell the same last item while offline.
- The server must resolve stock conflicts centrally.
- A temporary receipt is not a final invoice.
- Pending transactions must not create accounting entries or central stock movements before approval.
- Cash received during pending transactions requires a separately designed reconciliation process.

## 3. Browser and Device Compatibility
- Barcode scanning support varies by browser and device.
- Thermal printer compatibility must be tested on actual hardware.
- Bluetooth printing is not guaranteed on every Android device.
- PDF Arabic rendering requires proper font embedding and testing.

## 4. External Integrations
- Telecom and wallet APIs are not assumed to exist.
- No integration is considered active until credentials, documentation, and successful tests are available.
- WhatsApp integration requires an approved supported method.
- External service failures must not create false successful transactions.

## 5. Backups and Recovery
- GitHub is not a database backup.
- Supabase availability does not replace independent backups.
- Backups must include required attachments.
- Backup encryption keys must be stored separately.
- Backup readiness requires a successful restoration test.

## 6. Security
- Hiding a button is not sufficient authorization.
- Sensitive operations require server-side permission checks.
- Secrets must never be exposed in frontend code or public repositories.
- Employee internal email addresses must remain hidden.
- Audit records must be protected against unauthorized modification.

## 7. Accounting and Tax
- Tax registration status is not yet confirmed.
- Tax settings remain disabled until configured.
- Telecom commission accounting requires a detailed approved design.
- Financial reports must be reconciled against posted journal entries.

## 8. Production Readiness
- Development and production environments must remain separate.
- Supabase Free is for development and testing.
- Production capacity and plan requirements must be reviewed before real business use.
- No production launch before security, backup, recovery, and acceptance tests pass.

## 9. Open Design Decisions
- Final handling of cash received for temporary offline receipts.
- Detailed telecom and wallet accounting treatment.
- Offline synchronization ordering and conflict recovery.
- Backup retention and external storage provider.
- Final tax configuration.
- Invoice and thermal printer templates.
- Final visual identity based on the approved store logo.

## Completion Rule
Every limitation must have an owner-approved resolution or an explicitly documented accepted risk before production release.