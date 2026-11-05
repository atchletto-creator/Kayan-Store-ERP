KAYAN STORE ERP

Project Master Specification

1. Project Overview

Build a complete, professional, secure ERP system for KAYAN STORE in Egypt.

This is a new project from scratch. Do not assume any existing application, database, or legacy data.

The system must manage:

- Mobile accessories and electronics retail.
- Inventory and warehouses.
- Point of Sale (POS).
- Purchases, suppliers, and customers.
- Sales, returns, and exchanges.
- Mobile recharge and telecom services.
- Electronic wallets and InstaPay.
- Mobile and electronics maintenance.
- Cash treasury and accounting.
- Employees, attendance, and wages.
- Online orders and delivery.
- Reports, notifications, and audit logs.

2. Technical Foundation

- Database: Supabase PostgreSQL.
- Backend: secure server-side business logic.
- Repository: GitHub.
- Application: responsive web application, installable as PWA where supported.
- Currency: EGP.
- Time zone: Africa/Cairo.
- Fiscal year: January 1 to December 31.
- Languages: Arabic (RTL), English (LTR), and Turkish (LTR).
- Support multiple branches and warehouses from the beginning.
- Start with one branch and one warehouse.

Choose a maintainable architecture and document all technical decisions.

Do not expose database secrets or service-role keys in frontend code.

3. Owner Control and Permissions

The owner must have full control over:

- Application settings and appearance.
- Navigation, pages, forms, and dashboards.
- Product categories and classifications.
- Prices, discounts, promotions, and minimum selling prices.
- Employee accounts and permissions.
- Financial and inventory settings.
- Reports, templates, and integrations.

Employees must not modify application structure, prices, or sensitive settings without authorization.

Permissions must be enforced by the backend, not merely by hiding interface elements.

All sensitive actions must be recorded in an immutable audit log with user, device, timestamp, action, and old/new values.

4. Inventory and Products

Every product must support:

- Name, SKU, barcode, description, image, category, brand, and model.
- Purchase cost and approved selling prices.
- Retail, wholesale, and customer-group prices.
- Variants such as colors and models.
- Variant-specific barcode, stock, cost, and price.
- IMEI or serial numbers where applicable.
- Supplier relationships.
- Minimum stock and reorder target.

Inventory must track opening stock, purchases, sales, returns, adjustments, reservations, and available quantities.

Use whole units only. Never allow fractional product quantities.

Every stock change must create a traceable stock movement.

Prevent negative inventory unless explicitly authorized by the owner.

Use Moving Weighted Average for inventory valuation.

5. POS and Sales

The POS must support:

- Barcode and product search.
- Product variants.
- Shopping cart and quantity editing.
- Customer selection.
- Approved prices and discounts.
- Cash, wallets, InstaPay, mixed payments, partial payments, and credit.
- Suspended sales and resuming them.
- Printable and PDF invoices.
- Returns and exchanges.

Support manual invoice items that do not affect inventory. Allow authorized users to register them as permanent products separately.

Do not deduct inventory until a sale is confirmed.

6. Purchases and Suppliers

Support supplier records, purchase orders, product costs, expenses, payment records, supplier balances, returns, and statements.

A purchase must be received and reconciled before closure.

Do not support partial receipt of a single purchase order. Differences between ordered and received quantities must be flagged and resolved before closing.

Never rewrite historical inventory costs when new purchases occur.

7. Customers and Credit

Support customer categories, customer history, loyalty points, balances, credit limits, partial collections, and statements.

Credit sales must not use an installment plan.

Only authorized users may exceed customer credit limits.

8. Telecom and Electronic Wallets

Support:

- Vodafone Egypt.
- Orange Egypt.
- e& Egypt.
- WE.
- Vodafone Cash.
- Orange Cash.
- e& Cash.
- WE Pay.
- InstaPay.

Track transaction amounts, actual provider costs, customer collections, fees, store commissions, supplier commissions, status, and receipts.

Store Commission and Supplier Commission must be separate.

Never assume a telecom provider API exists unless a real integration has been implemented and tested.

Only successful transactions may recognize completed commission revenue. Failed, pending, cancelled, or refunded transactions must not be treated as completed revenue.

9. Maintenance

Create unique maintenance orders with:

- Customer and device information.
- IMEI or serial number.
- Fault description and inspection.
- Device condition and accessories.
- Assigned technician.
- Spare parts and their inventory movements.
- Repair cost and final customer price.
- Deposit and outstanding balance.
- Expected and actual dates.
- Warranty and delivery confirmation.

Statuses:
Received, Inspection, Awaiting Customer Approval, Repairing, Waiting for Parts, Ready, Delivered, Cancelled.

10. Treasury and Accounting

Implement genuine double-entry accounting.

Include:

- Chart of accounts.
- Journal entries.
- General ledger.
- Trial balance.
- Income statement.
- Balance sheet.
- Cash treasury accounts.
- Customer and supplier accounts.
- Wallet accounts.
- Revenue, expenses, COGS, returns, discounts, and taxes.

Every posted journal entry must balance.

Do not post the same transaction twice.

Correct posted transactions through reversal entries, not deletion.

Use DECIMAL for financial amounts, never FLOAT.

Internal transfers are neither revenue nor expenses.

11. Employees and Wages

Support employee profiles, roles, attendance, PIN-based clock-in/out, advances, deductions, and bonuses.

Initial hourly wage: 12 EGP per hour.

Overtime hourly wage: 12 EGP per hour.

Calculate wages by actual minutes worked.

Do not create employee commissions or assumed monthly salaries.

Only the owner can change the hourly wage.

Deduct wages from treasury only when payment is approved and actually made.

12. Online Orders and Delivery

Support online orders, customer addresses, products, shipping fees, tracking numbers, delivery status, COD, collections, delivery costs, returns, and profitability.

Support internal delivery representatives, assigned orders, cash custody, collections, expenses, and settlements.

13. Offline and Synchronization

The system must support genuine offline operation and multi-device synchronization.

Requirements:

- Local secure storage.
- Offline operation queue.
- Unique UUID for each operation.
- Idempotency to prevent duplicate transactions.
- Two-way synchronization.
- Conflict detection and resolution.
- Server confirmation before marking an operation synchronized.

Test inventory conflicts, including two devices selling the last available unit while offline.

Never claim offline support unless it has been implemented and tested.

14. Security and Audit

Implement:

- Secure password hashing.
- Server-side authorization.
- Session management.
- Login rate limiting.
- Owner multi-factor authentication.
- Remote employee session termination.
- Secure file uploads.
- Secrets management.
- Audit logging.
- Protection against duplicate financial operations.

15. Backup and Recovery

Provide automated backups, encrypted storage, off-server backup copies, and documented retention policies.

Test actual restoration of database and attachments.

Create a backup before major updates.

16. Reports and Data Export

Provide dashboards and reports for sales, purchases, stock, profits, expenses, customers, suppliers, wallets, telecom commissions, maintenance, wages, delivery, and accounting.

Financial reports must derive from the accounting ledger.

Support XLSX, CSV, and PDF exports where appropriate.

Support Excel imports with validation, preview, duplicate detection, and error reports.

17. WhatsApp and Notifications

Where a supported provider is available, integrate WhatsApp Business messaging for order confirmations, invoices, delivery updates, maintenance updates, and payment reminders.

Support OTP authentication through WhatsApp only when a real provider integration is configured and tested.

Provide an in-app notification center and owner alerts for sensitive actions.

18. Interface and Design

Use a professional Luxury Light Theme by default.

Do not force black and gold. Extract brand colors from the official KAYAN STORE logo when provided.

The interface must be responsive on mobile, tablet, and desktop.

Arabic is the default RTL language.

Provide consistent navigation, readable tables, accessible forms, clear validation, loading states, and reliable error handling.

All buttons and forms must perform real backend operations.

19. Development Rules

- Build in documented phases.
- Use real persistent database operations.
- Never use fake buttons or simulated integrations.
- Never insert demo data into production.
- Never claim a feature is complete without testing it.
- Preserve existing project work.
- Document database schema and business rules.
- Keep migrations version-controlled.
- Use secure Row Level Security policies.
- Keep all sensitive business logic server-side.

20. Acceptance Testing

Test all major workflows, including:

- Product creation and editing.
- Inventory movements and variants.
- Barcode scanning.
- Manual and mixed POS invoices.
- Purchases and supplier payments.
- Credit sales and collections.
- Returns and exchanges.
- Treasury and wallet operations.
- Telecom commissions and failed transactions.
- Maintenance and spare parts.
- Attendance and hourly wage calculations.
- Owner permissions and audit logs.
- Excel imports and PDF invoices.
- Backup and restore.
- Multi-device synchronization.
- Offline conflict resolution.
- Responsive mobile and desktop operation.
- Accounting balance and duplicate prevention.

For each test, document expected result, actual result, Pass/Fail, and any errors.

21. Implementation Roadmap

1. Architecture and technical design.
2. Database schema, authentication, permissions, and audit.
3. Owner control center.
4. Products and inventory.
5. POS and barcode.
6. Purchases, suppliers, and customers.
7. Treasury and accounting.
8. Telecom and wallets.
9. Maintenance.
10. Employees and wages.
11. Online orders and delivery.
12. Reports and global search.
13. Offline synchronization.
14. Security, backup, notifications, and updates.
15. Integration and acceptance testing.

Final Delivery Requirement

Deliver a genuinely working, deployable ERP application, not merely a design or implementation plan.

Report completed modules, database tables, integrations, actual test results, known limitations, remaining work, deployment requirements, and owner account initialization instructions.

Prioritize data integrity, accounting correctness, inventory accuracy, security, owner control, synchronization, and usability over appearance alone.