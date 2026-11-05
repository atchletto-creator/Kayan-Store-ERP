# KAYAN STORE ERP — Test Plan

All tests must be performed in the development environment.
Never use real production data for testing.

## 1. Authentication and Permissions
- [ ] Owner can sign in securely.
- [ ] Employee can sign in using username and password.
- [ ] Public self-registration is blocked.
- [ ] Duplicate usernames are rejected.
- [ ] Unauthorized users cannot access restricted operations.
- [ ] Server-side permission checks prevent unauthorized changes.
- [ ] Session revocation works correctly.
- [ ] Sensitive actions appear in the audit log.

## 2. Products and Inventory
- [ ] Product creation and editing work correctly.
- [ ] Duplicate SKU and barcode handling is correct.
- [ ] Stock quantities accept integers only.
- [ ] Unauthorized negative stock is rejected.
- [ ] Every stock change creates a stock movement.
- [ ] Moving Weighted Average cost is calculated correctly.
- [ ] Historical transaction costs remain unchanged.
- [ ] Returns use the original transaction cost.
- [ ] Multi-warehouse stock remains separated.

## 3. Accounting
- [ ] Every journal entry has equal debit and credit totals.
- [ ] Unbalanced journal entries are rejected.
- [ ] Duplicate posting is prevented.
- [ ] Posted journal entries cannot be edited or deleted.
- [ ] Reversal entries correct posted transactions.
- [ ] Internal transfers do not create revenue or expenses.
- [ ] Trial balance agrees with the general ledger.
- [ ] Financial reports reconcile with posted entries.
- [ ] Monetary calculations use exact decimal values.

## 4. Sales and Payments
- [ ] Cash sales post correctly.
- [ ] Wallet and InstaPay payments are recorded correctly.
- [ ] Mixed payments are supported.
- [ ] Partial payments are recorded correctly.
- [ ] Credit sales update customer balances correctly.
- [ ] Discounts require appropriate permissions.
- [ ] Returns reverse the correct financial and stock effects.
- [ ] Invoice numbers remain unique.

## 5. Purchasing and Suppliers
- [ ] Purchase orders are recorded correctly.
- [ ] Full receiving updates inventory correctly.
- [ ] Partial receiving is rejected.
- [ ] Receiving discrepancies must be resolved before closure.
- [ ] Supplier payments update balances correctly.
- [ ] Purchase returns are recorded correctly.

## 6. Telecom and Wallet Services
- [ ] Default balance source is selected correctly.
- [ ] Unauthorized source changes are rejected.
- [ ] Actual source is recorded for each transaction.
- [ ] Store and supplier commissions remain separate.
- [ ] Failed transactions do not recognize commission revenue.
- [ ] Repeated requests do not create duplicate transactions.

## 7. Employees and Attendance
- [ ] Attendance PIN is separate from login credentials.
- [ ] Work time is calculated by actual minutes.
- [ ] Unpaid breaks are deducted correctly.
- [ ] Early attendance requires authorization.
- [ ] Attendance corrections require a reason.
- [ ] Old and new attendance values are recorded.
- [ ] Wage calculations round correctly to the nearest piastre.

## 8. Repair Orders
- [ ] Each repair order has a unique identifier.
- [ ] Device and IMEI information are recorded correctly.
- [ ] Repair status changes are tracked.
- [ ] Spare parts create inventory movements.
- [ ] Deposits and remaining balances are calculated correctly.
- [ ] Delivery and warranty information are retained.

## 9. Offline and Synchronization
- [ ] Approved operations can be recorded offline.
- [ ] Pending operations remain visible.
- [ ] Reconnection triggers synchronization.
- [ ] Repeated synchronization does not duplicate transactions.
- [ ] Conflicting last-item sales are held for review.
- [ ] Temporary receipts are not treated as final invoices.
- [ ] Pending cash is reconciled without premature accounting entries.
- [ ] Local and central invoice numbers remain unique.

## 10. Backup and Recovery
- [ ] Scheduled backup completes successfully.
- [ ] Backup failure generates an alert.
- [ ] Backup includes required attachments.
- [ ] Encryption keys are stored separately.
- [ ] Restoration succeeds in a separate test environment.
- [ ] Restored records are checked for consistency.

## 11. User Interface and Compatibility
- [ ] Arabic RTL layout works correctly.
- [ ] English and Turkish LTR layouts work correctly.
- [ ] Mobile screens are usable.
- [ ] Barcode scanning is tested on supported devices.
- [ ] Arabic PDF text renders correctly.
- [ ] Thermal printing is tested on actual printers.

## Release Criteria
- [ ] Critical security tests pass.
- [ ] Accounting and inventory tests pass.
- [ ] Backup restoration test passes.
- [ ] Offline conflict tests pass.
- [ ] No critical unresolved defects remain.
- [ ] Owner approves production release.

A feature must not be marked as tested or complete without recorded test evidence.