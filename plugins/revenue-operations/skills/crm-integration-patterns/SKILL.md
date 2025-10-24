---
name: crm-integration-patterns
description: Integration architectures and patterns for connecting CRMs (Salesforce, HubSpot) with data warehouses, analytics platforms, and business systems. Use when designing data flows, building integrations, or troubleshooting CRM data sync issues.
---

# CRM Integration Patterns

Architectural patterns and best practices for integrating CRM systems with analytics, business intelligence, and operational tools to create unified revenue operations data infrastructure.

## When to Use This Skill

- Designing CRM to data warehouse sync architecture
- Building integrations between CRM and other business systems
- Troubleshooting data sync and integration issues
- Evaluating integration tools (Fivetran, Segment, custom APIs)
- Establishing data governance for revenue operations data
- Planning real-time vs. batch integration strategies

## Core Integration Patterns

### 1. ETL/ELT to Data Warehouse

**Extract-Transform-Load (ETL):**
```
Salesforce → API Extract → Transform → Load → Snowflake/BigQuery/Redshift
Frequency: Hourly or Daily
Tools: Fivetran, Stitch, Custom Python
Use: Historical analysis, BI dashboards, ML models
```

**Key Objects to Sync:**
- Accounts, Contacts, Leads
- Opportunities (current and historical snapshots)
- Activities (tasks, events, emails, calls)
- Users (sales rep assignments)
- Custom objects (products, quotes, etc.)

### 2. Bi-Directional Sync

**CRM ↔ Marketing Automation:**
```
Salesforce ↔ Marketo/Pardot/HubSpot
Sync: Leads, contacts, campaign responses
Frequency: Real-time or near-real-time
Pattern: Webhook-triggered or scheduled polls
```

### 3. Enrichment and Augmentation

**External Data → CRM:**
```
Clearbit/ZoomInfo → Salesforce
Data: Firmographics, technographics, contact data
Pattern: API calls on record creation/update
Use: Auto-populate account/contact fields
```

### 4. Operational Integrations

**CRM → Business Systems:**
```
Salesforce → ERP (NetSuite, SAP)
Trigger: Opportunity Closed Won
Action: Create customer record, initiate provisioning
Pattern: Real-time webhook or batch nightly
```

## Integration Architecture Decisions

**Real-Time vs. Batch:**
- Real-time: Operational workflows, alerts, immediate action needed
- Batch: Analytics, reporting, historical analysis

**API vs. Bulk:**
- API: Small volumes (<10K records/day), real-time
- Bulk API: Large volumes (millions of records), batch processing

**Push vs. Pull:**
- Push (Webhooks): CRM notifies external system of changes
- Pull (Polling): External system regularly queries CRM for updates

## Resources

- Salesforce API documentation
- HubSpot integration guides
- ETL tool comparison matrix
- Data warehouse schema templates

## Best Practices

1. **Idempotency:** Design integrations to handle duplicate API calls safely
2. **Error Handling:** Implement retry logic and dead letter queues
3. **Rate Limiting:** Respect API limits, implement throttling
4. **Monitoring:** Alert on failed syncs, data quality issues
5. **Data Governance:** Document data lineage and transformation logic
6. **Security:** Use OAuth 2.0, encrypt data in transit and at rest

## Common Pitfalls

1. **API Limit Exhaustion:** Exceeding daily API call limits
2. **Data Drift:** CRM and downstream systems out of sync
3. **Schema Changes:** Breaking integrations when CRM fields change
4. **No Error Visibility:** Silent failures, data missing
5. **Over-Syncing:** Syncing unnecessary fields/objects
6. **Performance Impact:** Heavy API usage impacting CRM performance
