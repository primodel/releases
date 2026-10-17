# Changelog

Customer-facing release notes for the Primodel container image (`ghcr.io/primodel/primodel`). Each version's SBOMs and verification instructions are on its [release](https://github.com/primodel/releases/releases).

## 6.1.0 — 2026-10-16

**New**
- Row-level security is now available for canonical stores on PostgreSQL and SQL Server.

**Fixed**
- Using a regular expression on a case-insensitive text column in your own SQL (table functions, data products, SQL sources) now returns a clear message explaining how to fix it.
- The enterprise demo now grants its personas access to the Customer Relationship domain.

**SBOM and verification:** see the [v6.1.0 release](https://github.com/primodel/releases/releases/tag/v6.1.0).

## 6.0.2 — 2026-10-15

**Security**
- Updated a cryptography library (System.Security.Cryptography.Pkcs) to address CVE-2026-84008 and CVE-2026-70162.

**SBOM and verification:** see the [v6.0.2 release](https://github.com/primodel/releases/releases/tag/v6.0.2).

## 6.0.1 — 2026-10-13

**Fixed**
- Fixed an issue where duplicate copies of a bundled code-editor library could cause the SQL/query editor to behave unpredictably.

**SBOM and verification:** see the [v6.0.1 release](https://github.com/primodel/releases/releases/tag/v6.0.1).

## 6.0.0 — 2026-10-12

**Breaking**
- PostgreSQL 18 is now the minimum supported version for the metadata and canonical databases. Canonical text comparison is now case-insensitive. Existing tables converge automatically on startup; any table whose keys differ only by letter case is reported and left unconverted until the operator resolves the conflict.

**New**
- SQL Server is now supported as a second canonical data store, including migration between providers.

**SBOM and verification:** see the [v6.0.0 release](https://github.com/primodel/releases/releases/tag/v6.0.0).

## 5.2.0 — 2026-10-11

**New**
- Plugin vendor licences (e.g., for certain database driver plugins) can now be accepted directly through configuration, without a separate manual step.

**SBOM and verification:** see the [v5.2.0 release](https://github.com/primodel/releases/releases/tag/v5.2.0).

## 5.1.2 — 2026-10-10

Maintenance release.

**SBOM and verification:** see the [v5.1.2 release](https://github.com/primodel/releases/releases/tag/v5.1.2).

## 5.1.1 — 2026-10-10

**Security**
- Updated base OS packages in the container image and pinned a bundled JavaScript dependency (source-map-js) to close known vulnerabilities.

**SBOM and verification:** see the [v5.1.1 release](https://github.com/primodel/releases/releases/tag/v5.1.1).

## 5.1.0 — 2026-10-07

**Improved**
- AI copilot setting changes now apply immediately, without requiring a restart.
- The AI copilot now separates its explanatory text more clearly from its tool-call output.
- Credential grants are now enforced consistently, and any adapter secret can reference a stored credential rather than only some.
- Reduced memory use when reading and writing Parquet files.

**Fixed**
- Fixed relationship (reference) field values sometimes resolving incorrectly during data ingestion.
- Upsert is now only offered for SQL export targets that actually support it, with case-insensitive column matching applied consistently across every supported database engine.
- A stale governed execution credential is now recovered automatically instead of causing the operation to fail.
- Target column matching for materialized exports is now case-insensitive.

**SBOM and verification:** see the [v5.1.0 release](https://github.com/primodel/releases/releases/tag/v5.1.0).

## 5.0.2 — 2026-10-04

**Fixed**
- Fixed existing data-lake ("silver") tables not evolving correctly against the REST catalog, and ensured they are re-exported automatically after an upgrade.

**SBOM and verification:** see the [v5.0.2 release](https://github.com/primodel/releases/releases/tag/v5.0.2).

## 5.0.1 — 2026-10-04

**Fixed**
- Upgrading no longer strands bundled plugins on an old version — they are now upgraded automatically along with the platform.
- Fixed reference fields not being expanded, and duplicate rows not being removed, in data-lake ("silver") tables.

**Security**
- The outbound-delivery (egress) allowlist is now enforced on every delivery path, and credentials no longer silently continue to be used after their target endpoint changes.

**SBOM and verification:** see the [v5.0.1 release](https://github.com/primodel/releases/releases/tag/v5.0.1).

## 5.0.0 — 2026-10-04

**Breaking**
- Data Product materialization has been removed from the API and UI; its columns are dropped. If you relied on a materialized Data Product, switch to querying it live.
- Egress pipelines using the Govern transform now withhold unclassified fields above the configured ceiling by default, unless explicitly allowed — review any pipeline that relied on unclassified fields passing through.
- Plugins built against a different major version of the Primodel SDK are now refused at load time; upgrade affected plugins to a compatible SDK version.

**SBOM and verification:** see the [v5.0.0 release](https://github.com/primodel/releases/releases/tag/v5.0.0).

## 4.0.3 — 2026-10-02

**Security**
- Updated OpenSSL/libssl3 in the container image to a patched version, closing known vulnerabilities in the shipped OS packages.

**SBOM and verification:** see the [v4.0.3 release](https://github.com/primodel/releases/releases/tag/v4.0.3).

## 4.0.2 — 2026-10-01

**Fixed**
- Fixed an issue with reference-field mappings.
- The web app no longer serves its own shell page in response to requests for API routes that have been removed; such requests now get a proper not-found response.

**SBOM and verification:** see the [v4.0.2 release](https://github.com/primodel/releases/releases/tag/v4.0.2).

## 4.0.1 — 2026-10-01

**Fixed**
- Fixed a migration that could silently drop part of the schema during an upgrade. Affected schema is restored by this release.

**SBOM and verification:** see the [v4.0.1 release](https://github.com/primodel/releases/releases/tag/v4.0.1).

## 4.0.0 — 2026-10-01

**Breaking**
- The "integration" concept has been renamed to "pipeline" throughout the product, including API routes and field names. Update any automation or scripts that call the old `/api/integrations`-style routes or reference "integration" terminology to use the new "pipeline" naming.

**SBOM and verification:** see the [v4.0.0 release](https://github.com/primodel/releases/releases/tag/v4.0.0).

## 3.1.12 — 2026-10-01

**Security**
- Resolved a set of known vulnerabilities in bundled application and web dependencies, including a YAML-parsing library (GHSA-r3ph-w7gj-g6xm).

**SBOM and verification:** see the [v3.1.12 release](https://github.com/primodel/releases/releases/tag/v3.1.12).

## 3.1.11 — 2026-09-28

Maintenance release.

**SBOM and verification:** see the [v3.1.11 release](https://github.com/primodel/releases/releases/tag/v3.1.11).

## 3.1.9 — 2026-09-27

Maintenance release.

**SBOM and verification:** see the [v3.1.9 release](https://github.com/primodel/releases/releases/tag/v3.1.9).

## 3.1.8 — 2026-09-27

Maintenance release.

**SBOM and verification:** see the [v3.1.8 release](https://github.com/primodel/releases/releases/tag/v3.1.8).

## 3.1.7 — 2026-09-26

**Improved**
- Support and sales contact addresses are now support@primodel.io and sales@primodel.io.

**Security**
- The published software bill of materials (SBOM) now lists bundled database driver plugins and their dependencies, improving vulnerability-scan coverage for the shipped image.

**SBOM and verification:** see the [v3.1.7 release](https://github.com/primodel/releases/releases/tag/v3.1.7).

## 3.1.6 — 2026-09-26

Maintenance release.

**SBOM and verification:** see the [v3.1.6 release](https://github.com/primodel/releases/releases/tag/v3.1.6).

## 3.1.5 — 2026-09-26

**Security**
- Hardened log output so untrusted values are always sanitised before they are written.

**SBOM and verification:** see the [v3.1.5 release](https://github.com/primodel/releases/releases/tag/v3.1.5).

## 3.1.4 — 2026-09-26

**Security**
- Vulnerability-scan results for each build stage are now published alongside the final image scan, improving supply-chain transparency.

**SBOM and verification:** see the [v3.1.4 release](https://github.com/primodel/releases/releases/tag/v3.1.4).

## 3.1.3 — 2026-09-25

**Security**
- Resolved eight known vulnerabilities in web application (frontend) dependencies.

**SBOM and verification:** see the [v3.1.3 release](https://github.com/primodel/releases/releases/tag/v3.1.3).

## 3.1.2 — 2026-09-25

**New**
- Signed releases can now be verified with a dedicated signing key, in addition to keyless verification.

**Fixed**
- Corrected a false warning claiming security updates would stop at expiry.
- Fixed data-quality evidence not being purged when an entity is deleted.
- Fixed orphaned retention data and a false-reclaim issue when a pipeline (integration) is deleted.
- Fixed licence/support-period expiry information not being available at runtime due to a missing file in the shipped image.

**SBOM and verification:** see the [v3.1.2 release](https://github.com/primodel/releases/releases/tag/v3.1.2).

## 3.0.0 — 2026-09-22

**Breaking**
- Schema apply/diff requests now carry relationships at the top level (with a separate list of deleted relationship ids), and reject a reference or collection field that has no relationship attached. The older per-field relationship properties are no longer accepted — update any automation that builds these requests directly.
- The Access API now returns capabilities as `{name, description}` objects instead of plain strings.
- Audit log entries now carry a separate target-name field instead of embedding the name inside the target reference — update any code that parses audit entries.
- The table-function and Data Product "execute" actions that were only used by the web app have been removed from the UI; the underlying REST endpoints are unchanged and still work.

**New**
- A single, unified relationship model now covers both entity reference and collection fields.
- Editors can run a governed test of a change before applying it.
- The governed AI assistant (MCP) tool surface now has parity for the Integrator role.

**Fixed**
- Installing a plugin package now clearly shows that it succeeded, instead of appearing to do nothing.
- Fixed several web UI utility classes (including status colors) that were silently dropped from the build.

**SBOM and verification:** see the [v3.0.0 release](https://github.com/primodel/releases/releases/tag/v3.0.0).

## 2.1.0 — 2026-09-08

**New**
- Plugins bundled in the image now install themselves automatically on first startup.

**SBOM and verification:** see the [v2.1.0 release](https://github.com/primodel/releases/releases/tag/v2.1.0).

## 2.0.2 — 2026-09-08

**Fixed**
- Fixed the released image shipping with no plugins installed at all.

**SBOM and verification:** see the [v2.0.2 release](https://github.com/primodel/releases/releases/tag/v2.0.2).

## 2.0.1 — 2026-09-07

**Breaking**
- Plugin packages are now distributed as signed NuGet packages (`.nupkg`) instead of `.zip` archives. A plugin installed before this release will not load after upgrading — reinstall each affected plugin from a 1.1.0 or later package (bundled plugins in the image are already updated).

**New**
- Oracle is now supported as an export target, and Db2 can feed the canonical model as an additional data source.
- Db2 is now a full export target, with schema introspection, scaffolding, and upsert (MERGE) support.
- Connection usage can now be granted to a role without requiring full administrator access.
- SQL connections can specify their own TLS trust settings, with any certificate-validation bypass clearly labeled as such.
- Added visibility and alerting for a growing ingestion backlog, so a slowdown is visible before it becomes an outage.

**Improved**
- The audit log is more readable, and an authorization gate now fails closed instead of open on error.
- The Validate button in the table-function editor now only checks the SQL; it no longer publishes a new version.

**Fixed**
- Fixed bundled database driver plugins that could be installed and marked active but never actually load.
- Several failure conditions that previously gave no information now report a clear, actionable error.
- Fixed a container startup failure caused by incorrect line endings in an internal script.
- Fixed plugin package signature verification referencing the wrong certificate.
- Fixed table functions not appearing under their data domain and not being visible to schema introspection.
- Fixed steward-reviewed/corrected rows not being preserved across snapshots, and reference fields not honoring the target's key type.
- Fixed reference (foreign-key) field values not being included on every read path, only on list views.
- Fixed a bug where saving a connection through the editor could leave it unusable.
- Fixed S3 connections not correctly resolving their endpoint from the configured region.

**SBOM and verification:** see the [v2.0.1 release](https://github.com/primodel/releases/releases/tag/v2.0.1).

## 1.5.0 — 2026-08-30

**Breaking**
- Data stores are now canonical-only; the "external database" data-store type has been removed. Existing external-database connections need to be reconfigured using the newer Connection/export model.
- Webhooks no longer use a separate, webhook-specific authentication layer — senders now authenticate as API clients. Any webhook secret configured the old way needs to be migrated to an API client.

**New**
- A dedicated Connection entity for managing endpoint credentials and settings, with a test/probe button to verify connectivity before saving, and scheduled health checks that alert only when status changes (not on every repeated failure).
- A webhook can now be configured to alert if it goes silent (receives no deliveries) for too long.
- A registered webhook sender's signature convention, header name, and certificate can now be edited after creation.
- A new static API-key authentication type (a token sent in a header).
- Mutual-TLS (mTLS) client authentication, where the client's certificate itself is the identity.
- Common webhook signature-verification conventions used by major vendors are now supported out of the box.
- Connection-scoped permissions, and finer-grained platform capabilities that can be granted independently of full administrator access.

**Improved**
- Literal connection secrets are now encrypted at rest; secret references are stored as pointers rather than copies.
- The API client form now asks only for what each authentication type actually needs, and clarifies exactly what a signature covers.
- The "HMAC" API client authentication type is now called "Signature", and a client can use a preset signature scheme.
- The Data Product editor now opens to the route, test, and activity panels first.
- Input hints now describe the kind of system expected rather than naming a specific vendor.

**Fixed**
- Fixed signature conventions not actually being adjustable, and the "Custom" option not behaving as expected.
- Creating or editing a webhook can now include its sender allowlist.
- Fixed authorization checks that only handled one caller type (user or API client) on endpoints reachable by either.
- The AI copilot now shows a clear "restart needed" message instead of an internal error.
- Fixed opening a saved webhook crashing in some cases.
- The Overview tab is no longer shown before a Data Product has actually been created.

**SBOM and verification:** see the [v1.5.0 release](https://github.com/primodel/releases/releases/tag/v1.5.0).

## 1.4.0 — 2026-08-28

**New**
- Message-based sources (e.g., email, webhooks) can now capture the raw ("bronze") bytes they received, including for batch uploads.
- The data lake's processed ("silver") layer replicates from the change stream per entity, repairs drift on a schedule, and refuses a schema change that would lose data.
- Operators can set a retention horizon for raw ("bronze") lake data; enabling or disabling raw capture is now recorded in the audit log.
- Quarantined records can now show the original source evidence (raw bytes) they came from.

**Improved**
- The data-quality worklist count now appears on its tab even when the current page is empty.
- Raw ("bronze") lake captures now store the exact bytes received, rather than a re-serialized copy.
- Table Functions moved under Data Modelling in navigation; Data Products and Webhooks now have separate pages.

**Fixed**
- Manually deleted records are now tracked durably, so a delete is never lost on replay.
- Fixed a bug that could serve one record's source evidence (raw bytes) as another's.
- Fixed raw source data being reclaimed before the bronze or evidence features finished reading it.
- Table functions are now visible through the governed GraphQL API to every API client (previously invisible to all).
- Entities on external (non-canonical) data stores can no longer be mistakenly included in lake export.
- Webhook delivery to the lake no longer carries its own separate lake credentials.
- Fixed lake replication not resuming correctly after an interruption.
- Fixed lake listings failing on an empty result.
- Table functions now appear in navigation for the role that authors them.
- Fixed a missing-plugin alert that could crash the application at startup; a missing plugin no longer blocks startup.
- Fixed quarantine record updates silently dropping columns.
- Job numbers and version numbers shown in the UI are now accurate.
- Editing a table function's SQL now clears a stale validation error.

**SBOM and verification:** see the [v1.4.0 release](https://github.com/primodel/releases/releases/tag/v1.4.0).

## 1.3.0 — 2026-08-25

Maintenance release.

**SBOM and verification:** see the [v1.3.0 release](https://github.com/primodel/releases/releases/tag/v1.3.0).

## 1.2.1 — 2026-08-24

**Fixed**
- Fixed a uniqueness data-quality rule that incorrectly flagged every row as a duplicate of itself.

**SBOM and verification:** see the [v1.2.1 release](https://github.com/primodel/releases/releases/tag/v1.2.1).

## 1.2.0 — 2026-08-24

**New**
- New data source adapters: FHIR R4, HL7v2, Protobuf, Arrow IPC, OData v4, LDAP/Active Directory, SCIM, MongoDB change streams, DuckDB, and SQLite.
- New change-data-capture (CDC) sources for MySQL (binlog), SQL Server (native change tables), and PostgreSQL (logical replication).
- New export/delivery targets: SQL Server, MySQL, Oracle, ClickHouse, and IBM Db2.
- AS2 transport support for EDI exchanges (S/MIME signing/encryption, MDN receipts), plus X12 and EDIFACT message format support, and a trading-partner management screen.
- Email (IMAP/POP3) as a data source.
- New connectors for Salesforce and Zendesk, both with PII masking applied.
- A new "Data Store Integrator" role that can author governed queries and table functions without needing full administrator rights.
- Author and deploy custom, read-only SQL query functions (table functions), governed and executed with parameter binding, row caps, and timeouts.
- Data Products can run live or be materialized, with automatic sensitivity-classification suggestions for output columns based on data lineage.
- Webhook signature templates for Stripe, GitHub, and Shopify, and a SuccessFactors webhook authentication scheme.
- An activity feed for Data Products and webhooks that never exposes the underlying data values.
- JWT Bearer authentication for HTTP connections.
- A dedicated admin screen for managing credentials, with inline credential creation when configuring a connection, a view of what would be affected before changing or rotating a credential, and zero-downtime credential rotation with an overlapping validity window.
- HashiCorp Vault, AWS Secrets Manager, and Azure Key Vault support for storing secrets externally.
- Alerts when a credential is nearing expiry.
- Self-referencing (hierarchical) entities, for modelling things like org charts or category trees, with keyboard-accessible, virtualized tree views.
- An admin UI for configuring the data lake connection and the outbound-delivery (egress) allowlist, plus Google Cloud Storage and local-filesystem storage options for the data lake.
- Credential pickers now support multi-select instead of free-text entry.

**Improved**
- Endpoint credentials can now be managed by Integrators and Owners, not only administrators.
- Clearer, more specific error messages when an outbound delivery is blocked by the egress allowlist, with guidance on how to fix it.
- SQL query autocomplete and inline validation for canonical data stores, including a dry-run validate option before running a query.
- Credential forms now show the specific fields each connector needs, instead of one generic secret field.
- More reliable data-lake commits on S3 and local filesystem storage.
- Faster loading for large hierarchical entity trees.
- Preview masked output columns before saving a Data Product.
- Pin a survivorship "winner" value directly from its cell; pins apply immediately and can be reviewed and undone later.
- Table function output columns are now detected automatically instead of requiring the author to type them.
- The API client permission editor now scales to many entities instead of showing one giant grid.

**Fixed**
- EDI messages above the configured size limit are now rejected instead of silently truncated, and delimiter characters inside EDI fields are now escaped correctly.
- Fixed AS2 message-integrity checking and MIME parsing issues.
- Domain Owners can now see Configure and field-layout screens that had been incorrectly restricted to them.
- Fixed a startup failure related to the email (IMAP) source.
- SQL validation errors now show the actual database error message instead of a generic "unreachable" message.
- Fixed a gap that let a non-administrator user list credentials without the required role.
- A data-type conversion error during ingestion now quarantines the affected record instead of crashing the whole batch.
- Hierarchy detection now works automatically when an entity has exactly one self-referencing field.
- Fixed a configuration error that could prevent the application from starting.
- Fixed hardware-security-module (HSM) key wrap/unwrap failures, including with certain HSM modules.
- Fixed a key-rotation defect in secret encryption.
- Fixed a crash loop on fresh installs related to secret-encryption key setup.
- Fixed reading/writing relationship-backed reference fields silently doing nothing in some cases.
- Fixed JSONPath record extraction when a secondary field path shares a prefix with the main records path.
- Fixed a disabled placeholder item appearing highlighted as if it were selected.
- Fixed startup failures affecting OData, GraphQL, and webhook endpoints.
- Dangling entity references are now rejected before a schema change is applied, instead of after.
- Dropdown labels now display acronyms correctly instead of a generic name.
- Manual survivorship with no override now correctly leaves the field empty instead of keeping a stale value.
- Extension packages are now verified before being loaded, and a bad extension can no longer stall background processing across the whole cluster.
- Fixed dangling data-lineage provenance badges covering the node above them.
- The data-quality steward view now explains what is conflicting and lets the steward unmask it for review.
- The quarantine dashboard no longer reports an unmeasured signal as a failure.
- Distinguished "no source data available" from an actual data-loss condition.
- Fixed survivorship pins not resolving to the intended field or record in some cases.
- Resolved decisions no longer reappear in the remediation queue; field groups no longer render twice.
- Fixed a valid zero byte-offset being discarded during data-record tracing.
- The conflict queue now refreshes correctly after resolving a pin.
- Browser password managers no longer try to autofill credential or data-store fields.
- Various pipeline-builder, hierarchy-tree, and list-view display fixes (step-card alignment, tree indentation, column resize, no-access vs. empty-list messaging).

**Security**
- Table functions execute as parameter-bound, read-only, row-capped, and timeout-bounded queries.
- Plugin packages are now verified against a trust anchor before loading, and fail closed if verification cannot be completed.
- Data Products now deny access below the caller's clearance instead of masking the result.
- Fixed a race condition that could let a plugin package be activated before its verification had actually completed.
- Discovery tools for OData, GraphQL, and WSDL sources are now enforced as read-only.
- Closed a connection-string injection vulnerability in startup/bootstrap configuration.
- Closed a remote-code-execution vulnerability in the SQL query path available to the Integrator role.

**SBOM and verification:** see the [v1.2.0 release](https://github.com/primodel/releases/releases/tag/v1.2.0).

## 1.1.0 — 2026-08-13

**New**
- Data quality workbench — a triage queue of records needing attention, with in-place remediation (fix & replay, accept, or discard) and history.
- Master data management — multi-source records with survivorship into a golden record, version history, and clear source provenance.
- Governed outbound integrations — an administrator-managed allowlist for where data may be sent.
- Zero-config demo — a one-command sample dataset for evaluating the platform.

**Fixed**
- Numerous data-grid, masking, and workbench usability improvements.

**SBOM and verification:** see the [v1.1.0 release](https://github.com/primodel/releases/releases/tag/v1.1.0).

## 1.0.0 — 2026-08-11

**New**
- Canonical information model — entities, fields, relationships, and data domains, authored visually or as version-controlled YAML.
- Governance — per-domain, cumulative role-based access control; field-level classification and clearance-based masking with audited unmask; an append-only, signature-based audit log.
- Data quality — two-stage validation (per-record and cross-record) with uniqueness, referential, and anomaly rules, batch circuit breakers, versioned rule lifecycle, and a steward workbench (quarantine review, replay, correct, override).
- Master data management — multi-source tables and field-level survivorship (source priority, most-recent, most-complete, manual pins) producing governed golden records with per-field provenance and reconciliation.
- Integrations — scheduled and change-data-capture triggers, source-to-target adapters (SFTP, HTTP, Kafka, database, object storage, email), plus governed push and query APIs.
- Log-based CDC ingestion and governed GraphQL egress.
- Data lineage — trace every value to its source system and ingestion run, and every delivery to its target.
- Governed AI assistant / MCP surface — bound by the same masking, grants, and audit as its user.
- Monitoring and alerting — data-quality thresholds with email and Slack notifications, plus quality trend charts.
- GDPR Article 30 records of processing — annotate fields with purpose, legal basis, and data-subject category; generate a grant-scoped, coverage-aware record and export it.

**SBOM and verification:** see the [v1.0.0 release](https://github.com/primodel/releases/releases/tag/v1.0.0).
