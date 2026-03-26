# n8n Automation Workflows

Production-grade automation workflows built with n8n, demonstrating API integration, conditional logic, error handling, and alerting.

## Workflow 1: Exchange Rate Monitor — NGN/USD Alert Pipeline

**Purpose:** Monitors USD/NGN exchange rates via API and triggers alerts when rates cross defined thresholds.

**Architecture:**
- Schedule Trigger (every 5 min) → HTTP Request (exchange rate API) → Conditional check → Alert formatting or No Action
- Error handling on API failures with structured error output
- Both success and failure paths handled explicitly

**Nodes:**
- Every 5 Min - Rate Check (Schedule Trigger)
- Fetch USD Exchange Rates (HTTP Request with error handling)
- Check NGN Above Threshold (IF condition)
- Format Rate Alert (Code node — TRUE path)
- Below Threshold - No Action (No Operation — FALSE path)
- Handle API Failure (Code node — error path)

**Key features:**
- Modular, reusable design
- Error handling with continue-on-error pattern
- Clear node naming for team readability
- Both conditional paths handled (no silent failures)

**How to use:**
1. Import `exchange-rate-monitor.json` into n8n
2. Adjust threshold value in the IF node
3. Connect alert output to Slack/Email/Telegram as needed
4. Activate the workflow

## About

Built by Tobenna Onyiriuba — IT Infrastructure & Integrations Engineer specializing in cross-platform automation, API integrations, and AI-powered workflows.
