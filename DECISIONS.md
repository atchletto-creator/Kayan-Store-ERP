# KAYAN STORE ERP — Approved Decisions

This file records decisions explicitly approved by the project owner.
Any change requires the owner's approval.

## General
- Business currency: EGP.
- Timezone: Africa/Cairo.
- Financial year starts on January 1.
- Default interface language: Arabic (RTL).
- English and Turkish are also supported.
- Start with one branch and one warehouse.
- The system must support multiple branches and warehouses.
- Use a Luxury Light Theme.
- Final colors must be derived from the approved store logo.

## Business and Operations
- Product quantities must be integers; no fractional stock.
- Negative stock is blocked unless explicitly approved by the owner.
- Inventory changes must be recorded as stock movements.
- Product costs use Moving Weighted Average.
- Historical transaction costs must be preserved.
- Partial purchase receiving is not allowed.
- Credit sales are supported without installment plans.
- Partial customer payments are supported.

## Accounting
- Use double-entry accounting.
- Every posted journal entry must balance.
- Posted entries cannot be edited or deleted.
- Corrections must use reversal entries.
- Internal transfers are not revenue or expenses.
- Use NUMERIC/DECIMAL for monetary values.
- Tax settings are disabled by default until configured.

## Employees and Permissions
- Employees log in using username and password.
- Employee email addresses are internally generated and hidden.
- No public self-registration.
- Attendance PIN is separate from login credentials.
- Standard hourly rate: 12 EGP.
- Overtime hourly rate: 12 EGP.
- Calculate working time by actual minutes.
- Breaks are unpaid by default.
- Early attendance requires authorized approval.
- Attendance corrections require a reason and audit record.
- Only the owner can change hourly rates.
- Sensitive permissions must be enforced on the server.

## Telecom and Wallet Services
- Supported operators: Vodafone Egypt, Orange Egypt, e& Egypt, and WE.
- Supported wallets: Vodafone Cash, Orange Cash, e& Cash, WE Pay, and InstaPay.
- Balance sources may include operators, distributors, and traders.
- The owner defines the default balance source for each operator.
- Employees may change the source only with permission.
- Store commission and supplier commission must be separate.
- No commission revenue is recognized before successful completion.
- No unverified API integrations.

## Offline and Conflicting Sales
- Full offline capability is a final project requirement.
- Offline functionality will be implemented gradually.
- Each device uses a unique temporary invoice number.
- Final invoice numbers are assigned centrally after approval.
- A conflicting sale for the last available item must remain pending.
- A temporary receipt is not a final invoice.
- No central stock deduction or accounting entry before owner resolution.
- The owner decides how to resolve the conflict.

## Security and Infrastructure
- Use Supabase PostgreSQL and Row Level Security.
- Sensitive operations must use secure server-side functions.
- No secrets or API keys in frontend code or GitHub.
- Development and production environments must be separate.
- Supabase Free is used during development and testing.
- Review the appropriate plan before real production operation.
- Backups must be independent of GitHub and Supabase.
- Backup restoration must be tested before claiming backup readiness.

## Development Rules
- Accounting, cash management, and inventory take priority over POS.
- Database schema must be reviewed before table creation.
- No fake buttons or simulated integrations.
- Every feature must be tested before being marked complete.
- Record changes and important decisions.