# Breakthru Sales Management Plugins

Cowork plugin marketplace for Breakthru Beverage Group field sales management workflows in Palm Beach County.

## Plugins

| Plugin | Description |
|--------|-------------|
| **note-parser** | Parse rep daily reports and ride-with recap notes into structured data |
| **program-tracker** | Track and consolidate 21 supplier programs across varied formats |
| **territory-reviews** | Weekly territory performance reporting and rep analysis |
| **job-search** | Track job applications, contacts, and follow-ups |

## Installation

```bash
# Add the marketplace
claude plugin marketplace add <path-or-repo>/breakthru-sales

# Install plugins
claude plugin install note-parser@breakthru-sales
claude plugin install program-tracker@breakthru-sales
claude plugin install territory-reviews@breakthru-sales
claude plugin install job-search@breakthru-sales
```

## Data Boundary

Company-proprietary data (account lists, pricing, distributor reports) is handled through BBG's internal AI tool. These plugins process data provided at runtime — no company data is embedded in the plugins themselves.
