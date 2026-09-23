# Hybrid Transition Flow

## Objective

Move partner-facing B2B processing from Oracle SOA B2B to Oracle Integration B2B while preserving the existing SOA business logic, transformations, routing, and backend connectivity.

This workshop follows Oracle's Hybrid Transition pattern: Oracle Integration B2B owns the B2B edge, and SOA continues to own the established business processes. [Read the Oracle reference blog](https://blogs.oracle.com/integration/oracle-soa-b2b-to-oracle-integration-b2b-a-practical-modernization-path)

## Target Architecture

```text
Inbound

Trading Partner
      |
      v
Oracle Integration B2B
Agreement resolution | validation | B2B-to-XML translation | tracking
      |
      v
Oracle Integration Backend Integration
Map OIC XML to the SOA gateway schema
      |
      v
Lightweight SOA BPEL Gateway
Minimal mediation only
      |
      v
Existing SOA Composite
Existing transforms | rules | orchestration | routing
      |
      v
Backend Application

Outbound

Existing SOA Composite
      |
      v
Oracle Integration Outbound Integration
Accept the existing SOA business document
      |
      v
Oracle Integration B2B
Agreement resolution | XML-to-B2B translation | delivery | tracking
      |
      v
Trading Partner
```

## Flow 0: Establish the B2B Foundation

### Purpose

Prepare the pilot trading partner in Oracle Integration B2B before building inbound or outbound routing.

### Steps

1. Select one pilot trading partner and document type, for example an X12 850 Purchase Order.
2. From SOA B2B, collect or export the partner, agreements, identifiers, document definitions, schemas, and related configuration.
3. Use the supported migration utility to import the eligible B2B artifacts into Oracle Integration.
4. Review the imported trading partner, agreement, document definitions, and identifiers.
5. Configure or complete the transport channel:
   - AS2 or SFTP endpoint
   - Authentication credentials
   - Certificates, keys, and partner identifiers
   - Non-production delivery settings
6. Save the configuration and confirm the partner agreement is valid.

### Validation

- The pilot partner, agreement, and document definition appear in Oracle Integration B2B.
- The channel has the correct non-production endpoint and security configuration.
- No production endpoint, credential, or certificate is used.

## Learn More

* [Getting Started with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/application-integration/index.html)
* [Using the SOAP Adapter with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/application-integration/soap-adapter/index.html)
* [Using the REST Adapter with Oracle Integration 3](https://docs.oracle.com/en/cloud/paas/application-integration/rest-adapter/index.html)

## Acknowledgements

* **Author** - Subhani Italapuram, Director Product Management, Oracle Integration
* **Contributors** - Kishore Katta, Director Product Management, Oracle Integration
* **Last Updated By/Date** - Subhani Italapuram, Aug 2026
