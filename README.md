# APPLICAT-1 — Application to Prepare and File Accounts for Small Limited Companies in England

## Intent

### Problem

This application is designed specifically for small limited companies registered in England.

### Who it is for

The primary users are farm and packhouse teams who require a simplified and guided approach to preparing and filing accounts.

### What version one does

Version one provides a guided workflow to prepare accounts of a limited company as per England HMRC rules and make them ready to file.

## Scope

### In scope

- Guided data collection including bank transactions and other financial inputs.
- Preparation of draft and final accounts according to HMRC requirements.
- User review and approval workflow for final accounts.
- Electronic filing of returns following HMRC procedures.

### Out of scope

- Accounting services for companies outside England.
- Manual bookkeeping or bank transaction processing.
- Tax advice beyond general efficiency suggestions.
- Support for complex corporate structures or audits.

## System Context

The system consists of:

- Staff interacting via a Web UI.
- The Web UI communicates with the HTTP API.
- The API accesses fixture JSON data and exposes a health check endpoint.

## Components

- **Data Collection Module**: Guides users through collecting bank transactions and other financial inputs.
- **Accounts Preparation Engine**: Prepares draft and final accounts according to HMRC requirements.
- **User Review and Approval Interface**: Provides workflow for user review and approval of final accounts.
- **Electronic Filing Integration**: Handles electronic filing of returns following HMRC procedures.
- **Health Check Endpoint**: Provides a GET /health endpoint for system health monitoring.
- **Testing Fixtures**: Provides fixture data for unit and integration testing.

## APIs

| Method | Path                              | Purpose                                                |
|--------|----------------------------------|--------------------------------------------------------|
| GET    | /health                          | Deploy verify — report ok                              |
| GET    | /api/simplify-accounts-preparatio | Simplify accounts preparation for small limited companies. |
| GET    | /api/ensure-compliance-with-engla | Ensure compliance with England HMRC accounting and filing standards. |
| GET    | /api/provide-clear-user-friendly- | Provide clear, user-friendly guidance throughout the process. |
| GET    | /api/help-users-optimize-tax-mana | Help users optimize tax management efficiently.       |

## Request Flow

1. Staff opens the app via the Web UI.
2. The UI calls GET /health to verify system status.
3. Staff makes API calls to the endpoints for simplifying accounts preparation, ensuring compliance, providing guidance, and optimizing tax management.
4. The API reads or writes fixture JSON data as needed.
5. The API returns JSON responses to the UI.

## Technologies

- Node.js for the HTTP API and UI components.
- Python for the Accounts Preparation Engine, Electronic Filing Integration, and Testing Fixtures.

## Deployment

- Use existing Git connection "FileAccountsUK".
- Attach the connection in the pipeline.
- Set infrastructure to use existing resources.
- Run the pipeline targeting the **dev** environment.
- Rollback owner: Platform on-call.

## Assumptions

- The application targets only small limited companies registered in England.
- Users are primarily farm and packhouse teams with limited accounting expertise.
- HMRC rules and filing procedures are stable and accessible for integration.
- The system will comply with platform policies for testing and health checks.

## License

MIT
