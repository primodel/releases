## v8.3.1 — 2026-11-18

## New

- Field paths can address keys containing dots or slashes with bracket syntax, e.g. translations["white/blue"].
- An MCP tool lists the registered connections a caller may use, so agents can pick a cluster or database for a pipeline step.
- Unnest splits XML repeated elements and Parquet lists the same way it splits JSON arrays.

## Fixed

- JSON objects and arrays mapped to a text field land as JSON text again, instead of being stored as empty. Re-run affected pipelines to restore the values.
- A value that can't be converted to its target type is quarantined with a reason, never silently stored as empty.
- Change-log pruning on large logs no longer times out, and an index is added in the background without blocking writes.
- The lineage toolbar's pipelines toggle is no longer clipped, and edge tooltips show the pipeline name and its status on separate lines.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v8.3.1) — `primodel-8.3.1-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:8.3.1
```

## v8.3.0 — 2026-11-18

## New

- Retire a source tag from a multi-source entity with a preview first; it refuses while a pipeline or survivorship rule still uses the tag, and every retirement is audited.
- Change an entity's table mode (multi-source, soft delete, retention) from the entity page, with a preview of exactly what each change does before it's confirmed.
- On-change schedules can watch specific entities.
- Query Workbench's Promote to SQL source opens the pipeline editor with the query prefilled.

## Improved

- Secret settings show whether a value is set without ever revealing it, in the UI, REST, MCP and YAML.
- Narrowing a text field's maximum length on an empty table is no longer flagged as destructive.
- Multi-source reference and uniqueness rules are explained in the UI and the docs.
- The change log drains a large backlog within hours instead of weeks.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v8.3.0) — `primodel-8.3.0-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:8.3.0
```

## v8.2.0 — 2026-11-18

## New

- A store's change log is pruned automatically after a retention window (7 days by default) when no delivery binding needs the rows.
- System administrators can preview and trim a store's change log from the data store page or through MCP; every trim is audited.
- A new or re-enabled delivery binding starts from now by default, and shows how far back it can replay.

## Improved

- SFTP and S3 sources delete, move or archive a file only after its rows are committed, so a failed run leaves the file in place.
- Pipeline runs, previews and MCP tools check that the referenced connections are still allowed for the caller.
- Startup fails with a clear message when the object store folder can't be written.

## Fixed

- Effective-from and effective-until dates keep their calendar date regardless of the server's time zone.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v8.2.0) — `primodel-8.2.0-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:8.2.0
```

## v8.1.1 — 2026-11-17

## Fixed

- AI features (Copilot, Fix with AI) work behind gateways and firewalls that reject requests without a User-Agent; every outbound call now identifies itself as Primodel.
- AI errors distinguish a rejected API key from a request refused by a gateway or firewall.
- Changing a runtime setting such as the AI API key takes effect on every node without a restart.
- Two concurrent writes that start the same new effective-dated period no longer conflict or deadlock.
- Large CSV and fixed-width files no longer slow down from excessive memory growth while decoding.
- The ingest diff explainer no longer reports every row of a plain or multi-source entity as having a stale hash.
- Dropdown settings no longer appear to have a value selected when none is stored; unset settings show their default.
- The connection editor is wide enough to show its access list without horizontal scrolling.
- The demo data shipped with the getting-started stack matches the generator again.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v8.1.1) — `primodel-8.1.1-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:8.1.1
```

## v8.1.0 — 2026-11-17

## New

- Query Workbench can reveal the masked values of a single result row; each reveal is audited.
- Pipelines have an Unnest transform that emits one record per array element, carrying the parent's fields.
- SFTP and S3 sources can delete, move or archive a file after it has been ingested.
- Kafka steps can pick which registered Kafka connection to use, and change-data-capture sources (Postgres, SQL Server, MySQL, MongoDB) can read from a registered external connection.

## Improved

- Every step setting is a proper form field; steps without settings say so instead of showing a JSON box, and encodings and compression levels are dropdowns.
- The Versions and Sources dialogs open revealed and can pivot to show only changed fields.
- System columns on the Data tab fit their content and can be resized.
- Aggregates, distinct values and counts accept system columns such as `__source`.
- Pushing records into a plain entity is up to 13 times faster.
- The demo seed only adds what is missing, so it is safe to run on an existing demo install.

## Fixed

- Query Workbench reports a timeout as a timeout, with a suggested rewrite, instead of an opaque error, and Fix with AI says when AI is not configured.
- Equal decimal values with different trailing zeros no longer register as a change.
- Unique fields get their unique index when a table is first created or a field is added.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v8.1.0) — `primodel-8.1.0-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:8.1.0
```

## v8.0.0 — 2026-11-17

## Breaking

- SDK contracts improved and consolidated; plugins must be rebuilt against Primodel SDK 4.

## Fixed

- Data grid column-group headers now line up with their columns.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v8.0.0) — `primodel-8.0.0-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:8.0.0
```

## v7.14.8 — 2026-11-16

## Fixed

- a golden (survivorship) entity with an effective-dated history now correctly carries its data lineage through every read, instead of occasionally showing every field masked or failing with an error.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.14.8) — `primodel-7.14.8-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.14.8
```

## v7.14.7 — 2026-11-16

## Fixed

- Golden (survivorship) records with a sensitive field show the reveal/unmask control again, across every table shape (plain, effective-dated, multi-source, and version history).
- A data-domain migration's content-verification step no longer reports a false mismatch for a row whose only change was in a JSON-typed field.
- An exported lake/Iceberg snapshot writes the real content of a JSON-typed field instead of placeholder text.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.14.7) — `primodel-7.14.7-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.14.7
```

## v7.14.6 — 2026-11-16

## New

- Snake Case and Kebab Case field-mapping operators are available when authoring pipelines.

## Fixed

- Filtering, grouping, or looking up distinct values by a reference field's physical column name now works, not just its display name.
- An invalid filter field name on a data query now returns a clear error message instead of a generic failure, with a suggestion when a close match exists.
- Diagram edges no longer intermittently fail to render when a canvas first loads.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.14.6) — `primodel-7.14.6-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.14.6
```

## v7.14.5 — 2026-11-16

## New

- Added Snake Case and Kebab Case field-mapping operators for pipeline authoring.

## Improved

- The Source filter on the Data tab is now a multi-select panel, so you can filter by more than one source at once.
- SQL editor autocomplete now also suggests an entity's generated functions, not just its tables and columns, and offers a "did you mean" hint for near-miss names.

## Fixed

- Moving a box in a diagram and saving no longer pops up an unnecessary deploy review, and temporal read functions no longer get incorrectly flagged as out of date right after being recreated.
- A record's related-records tab now shows only that record's own related rows, instead of every row in the related table.
- Creating a new entity with a default value on a required field now applies that default correctly, instead of failing the first import that omits the field.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.14.5) — `primodel-7.14.5-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.14.5
```

## v7.14.4 — 2026-11-16

## Fixed

- A field default value is now validated against its declared type before a model deploy applies it, with a clear error naming the field when it doesn't match, instead of a generic failure.

## Security

- Fixed a field default value containing a quote or semicolon from being interpolated unescaped into the generated database schema change during a model deploy.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.14.4) — `primodel-7.14.4-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.14.4
```

## v7.14.3 — 2026-11-16

## Security

- The bundled FHIR, Google Cloud Storage, Azure Blob Storage, Amazon SQS, Amazon SNS and Amazon Kinesis connectors now re-check the destination address when connecting, closing a DNS-rebinding path to internal addresses.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.14.3) — `primodel-7.14.3-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.14.3
```

## v7.14.2 — 2026-11-16

## Security

- outbound connections from these connectors now re-check the destination address at connect time, closing a DNS-rebinding path to internal addresses.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.14.2) — `primodel-7.14.2-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.14.2
```

## v7.14.1 — 2026-11-15

## Improved

- Change detection during loads is faster and allocation-free, and JSON fields are compared in a canonical form, so reordered keys or whitespace no longer count as a change; the first reload after upgrading quietly refreshes stored fingerprints with no change events.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.14.1) — `primodel-7.14.1-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.14.1
```

## v7.14.0 — 2026-11-15

## Improved

- REST and MCP now accept a JSON or JSONB field's value as either a nested JSON object/array or JSON text when creating or updating a record.
- Ingestion now honours a per-record source, so each record in a batch can carry its own source instead of the whole batch sharing one.
- A new data snapshot now replaces only the sources actually present in that snapshot, leaving other sources' existing records untouched.

## Fixed

- JSON and JSONB field values now come back as proper nested JSON — not as escaped text — in REST responses, GraphQL, MCP, data products, and delivery.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.14.0) — `primodel-7.14.0-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.14.0
```

## v7.13.6 — 2026-11-15

## New

- A diagnostic explains why an incoming record was or wasn't treated as changed, column by column, without revealing values above your clearance.

## Fixed

- Reloading unchanged data into a multi-source effective-dated table now skips unchanged rows instead of re-comparing every row, so reloads where most rows are unchanged finish much faster; the first reload after upgrading quietly updates stored fingerprints, with no change events.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.13.6) — `primodel-7.13.6-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.13.6
```

## v7.13.5 — 2026-11-15

## New

- GraphQL now rejects unknown query arguments, filter fields, filter operators and type-mismatched filter values with a clear error instead of silently returning unfiltered rows.
- GraphQL exposes every system column an entity's mode carries (hash, sync cursor, created/updated timestamps, version, source, effective-dated bounds, retention expiry, lineage) as read-only fields.

## Improved

- entity mode indicators (effective-dated, history, multi-source, golden, hierarchical, retention, soft-delete) are now shown consistently, with a short explanation, everywhere an entity appears.

## Fixed

- a GraphQL query that joins into an effective-dated entity no longer fails when the joined column isn't text-typed.
- the change-detection fingerprint now normalises timestamps and decimals by declared column type, so the first reload of each effective-dated table after upgrading reports every row as changed once; later unchanged reloads are true no-ops.
- unmasking, updating, deleting, permanently erasing or viewing the version history of a record no longer fails on a multi-source or effective-dated row.
- the Versions dialog now shows whether each period is in the past, in force now, or upcoming (instead of labelling every period "live"), and formats date-only bounds without a timestamp.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.13.5) — `primodel-7.13.5-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.13.5
```

## v7.13.4 — 2026-11-15

## Improved

- Reloading unchanged effective-dated data no longer reprocesses previously terminated periods, so unchanged reloads finish much faster.

## Fixed

- The data lineage flow no longer flickers when the mouse moves quickly across it, and a selected node keeps its highlight while hovering others.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.13.4) — `primodel-7.13.4-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.13.4
```

## v7.13.3 — 2026-11-15

## New

- The lineage diagram now highlights a node's connected edges on hover or selection, shows distinct shapes per node kind, and can display pipelines as edges instead of boxes.

## Improved

- After upgrading, the first reload of tables with date fields or generated columns may report updates on unchanged rows once, as stored row fingerprints are recomputed.
- Ingestion traces now show a complete root-to-finish timeline, including time spent waiting in queue, for healthy runs as well as failed ones.

## Fixed

- Demo data seeding no longer fails on a fresh install when some rows are diverted to data-quality review.
- Reloading data with no real changes no longer repeatedly re-checks every row; a one-time fingerprint repair now also runs automatically when needed.
- Tables with computed (generated) columns no longer fail to load with a database error.
- Opening a record that belongs to a multi-source table no longer shows a "not found" error; an ambiguous record now shows a clear choice instead of a silent failure.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.13.3) — `primodel-7.13.3-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.13.3
```

## v7.13.2 — 2026-11-15

## Improved

- Database spans during ingestion are named by step and carry the parameterized SQL text, so traces show which statement took the time; a setting turns the SQL text off.
- Startup and idle installations emit far fewer traces: plugin loading is a single trace, and the change-outbox relay only traces when it delivers something.
- Loading effective-dated tables is much faster and its cost now scales with the number of changes instead of the size of the snapshot; reloading unchanged data writes nothing.
- Very large effective-dated loads now apply in bounded batches with steady memory use, and resume cleanly after an interruption.

## Fixed

- Telemetry from workers that shut down (for example when autoscaling scales in) is now flushed before exit instead of being lost.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.13.2) — `primodel-7.13.2-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.13.2
```

## v7.13.1 — 2026-11-14

## Improved

- The standard OTEL_EXPORTER_OTLP_* and OTEL_SERVICE_NAME / OTEL_RESOURCE_ATTRIBUTES variables are now honoured, and telemetry identifies the process role and version.
- Background database polling and health-probe requests no longer flood traces on an idle installation; settings turn each back on.

## Fixed

- Composite primary keys now follow the key's declared column order, and existing keys built in the wrong order are rebuilt online on upgrade without touching data.
- Setting an OTLP endpoint now turns on telemetry export, and startup logs whether traces, metrics and logs are being exported and where.
- Environment variables in the Section__Key form now override settings from configuration files, as documented.
- The cursor no longer jumps while typing in the Query Workbench.
- Query Workbench history and saved queries are left-aligned and show the start of each query.
- SQL and other validation errors now show the actual message instead of "Validation failed."

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.13.1) — `primodel-7.13.1-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.13.1
```

## v7.13.0 — 2026-11-14

## New

- Pipeline and lineage diagrams can be switched between left-to-right and top-down layout.

## Improved

- Relabelling a data source on a large table now runs in the background and can no longer be interrupted by a client timeout.
- SQL Server ingest for effective-dated tables is significantly faster on long correction chains.

## Fixed

- Golden records now refresh their lineage and provenance after a source relabel.
- Incremental and full golden recompute now converge to the same result for effective-dated tables.
- Plain entities now get a physical primary key on their business key, matching their declared schema.
- Non-temporal tables with survivorship merging no longer fail when they lack a supersede timestamp column.
- The relabel guard that refuses a conflicting pipeline now returns a clear error instead of a generic failure.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.13.0) — `primodel-7.13.0-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.13.0
```

## v7.12.2 — 2026-11-14

## Fixed

- Filtering records of an effective-dated entity by key returns only that record's periods, and the Versions dialog lists them for multi-source entities too.
- Putting a record source in a pipeline's source slot (or the reverse) explains which slot it belongs in, instead of asking for a format adapter.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.12.2) — `primodel-7.12.2-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.12.2
```

## v7.12.1 — 2026-11-13

## Improved

- Recomputing an effective-dated golden record set is much faster and drains a large backlog in a single run, committing as it goes so an interruption resumes rather than starting over.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.12.1) — `primodel-7.12.1-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.12.1
```

## v7.12.0 — 2026-11-13

## Improved

- Data Store Integrators can see blocking sessions on their data store, and domain Owners can see them with other domains' table names hidden.

## Fixed

- An incremental golden recompute reaches every key that needs it, including keys missing from the golden after earlier interrupted runs, and its retire step no longer scans the whole source.

## Security

- The runtime base image takes the glibc fix for CVE-2026-84243.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.12.0) — `primodel-7.12.0-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.12.0
```

## v7.11.0 — 2026-11-13

## New

- System administrators can see blocking sessions and lock waits on a data store.

## Improved

- Running recomputes show their current step and progress, and run diagnostics flag a run that has stopped making progress.
- Entity descriptions over MCP list collection (inverse reference) fields.

## Fixed

- A golden record recompute can no longer hang indefinitely: it fails with a message naming the step it was in, and large recomputes drain to completion across successive runs.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.11.0) — `primodel-7.11.0-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.11.0
```

## v7.10.1 — 2026-11-13

## Fixed

- A golden record recompute no longer stalls and times out at its start when another session is reading the survivorship override table, and its configured timeout now applies to every step.
- Re-checking a data quality rule no longer marks still-failing rows as corrected on multi-source entities, so violation counts and the quarantine queue match the data.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.10.1) — `primodel-7.10.1-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.10.1
```

## v7.10.0 — 2026-11-13

## Improved

- Effective-dated loads classify periods in the database, so their cost stays flat as tables grow into the millions of rows.
- Rolling upgrades drain traffic before an instance stops, so in-flight requests complete.
- Change events are no longer duplicated when a publish is retried.

## Fixed

- Golden records whose rules use reference fields recompute correctly.
- Recomputing an effective-dated golden record set of tens of thousands of periods completes in seconds instead of timing out, and overlapping recompute requests coalesce.
- A failed change of temporal mode no longer leaves stray columns or functions behind, and leftovers from earlier versions are cleaned up at startup.
- Emptying an entity or re-running a data quality rule no longer leaves stale quarantine findings, so violation counts match the data.
- Several new periods for one record in a single load all reach the lake, not just the last.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.10.0) — `primodel-7.10.0-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.10.0
```

## v7.9.0 — 2026-11-13

## New

- A "null if empty" value operator for field mappings.
- Versioned and effective-dated entities show one row per record with a Versions link to every version or period, including audited unmasking.

## Improved

- Runs that quarantine many rows finish much faster, and quarantine shows as its own phase with a live count.
- Entity descriptions over MCP include the physical primary key and unique constraints.

## Fixed

- Converting a golden entity to effective-dated keeps one row per period instead of rejecting a second period, and entities converted on an earlier version are repaired at startup.
- The overlap check when converting to effective-dated names the conflicting keys.
- Golden records built from effective-dated sources support periods with no start date (valid since forever).
- An enrichment that matches a lookup row with an empty value now writes an empty (null) value instead of an empty string.
- Effective-dated loads no longer lose field values on new periods that arrive in the same batch as a termination.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.9.0) — `primodel-7.9.0-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.9.0
```

## v7.8.1 — 2026-11-12

## Improved

- Ingestion publishes its change events much faster, so large uploads finish noticeably sooner.
- Effective-dated ingestion into tables that already hold history is faster.
- The Query Workbench fills the window; results scroll inside the table with a sticky header.

## Fixed

- The Query Workbench store and domain pickers no longer overlap.
- Viewing source variants for a golden record with a composite key no longer fails.
- A survivorship configuration with an over-long description is rejected with a clear message instead of a server error.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.8.1) — `primodel-7.8.1-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.8.1
```

## v7.8.0 — 2026-11-12

## New

- A Query Workbench for running governed, read-only SQL against a data store, with saved queries and history, also available to AI agents over MCP.

## Improved

- Survivorship configurations and their recompute pipelines can be read, versioned, provisioned and removed over MCP.
- Field layout (groups and order) can be set over MCP and in model-as-code.
- Model diffs report field-level authority and compliance changes.
- Long ingest runs report their phases and progress.
- SQL Server ingestion is substantially faster for plain, multi-source and history tables.
- Field impact analysis is exact for Data Products, table functions and outgoing pipelines.
- The Entities list shows and filters by temporal mode, and lineage edges highlight on hover.

## Fixed

- Loading effective-dated data with several periods per key is fast again: 30,000 rows take about half a minute instead of over 12, and an unchanged re-run takes seconds.
- Switching an entity, including a golden entity, to effective-dated no longer fails, and no longer asks for an effective-from field.
- Model-as-code applies `temporal: effectiveDated` as effective-dated rather than as history.
- Relationship lines reappear in entity diagrams after a referenced entity's key changed.
- A semicolon inside a string or comment no longer makes a SQL statement count as several.

## Security

- On SQL Server, a Data Product or table function column could carry another column's classification when the SELECT list wasn't in table order, so a sensitive value could be returned unmasked.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.8.0) — `primodel-7.8.0-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.8.0
```

## v7.7.1 — 2026-11-12

## Improved

- SQL sources and targets pick their data store or connection from a list, and a missing one is reported when you validate or save the pipeline.
- A newly queued run starts promptly on a node that has just taken over its work after a cluster rebalance.

## Fixed

- Run history now shows the time spent fetching from the source separately from the time spent queued, so a slow source no longer looks like a busy platform.
- A date or time without a time zone is read as UTC everywhere, so values no longer shift on servers that don't run in UTC.
- Times with a half- or quarter-hour offset (for example +05:30 or −03:30) keep their exact instant.
- Renaming a pipeline's source tag completes correctly even if the server stops partway through.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.7.1) — `primodel-7.7.1-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.7.1
```

## v7.7.0 — 2026-11-12

## New

- Pipeline lineage. A Flow view shows which systems and pipelines feed each entity, what each change triggers, and where data leaves, with step-by-step expansion. It is also available to agents through an MCP tool.
- An effective-dated entity's end date can be mapped from the source. A supplied end wins over the derived one, inclusive source dates convert automatically, and an overlapping period is quarantined rather than silently adjusted.
- The MCP record query can read past and future slices of effective-dated and versioned entities, and every row carries its period.
- An MCP tool versions a survivorship configuration.

## Improved

- Ingestion is many times faster in every table mode on both PostgreSQL and SQL Server. A 30,000-row update now takes seconds instead of a minute or more.
- Overlapping periods on effective-dated entities in PostgreSQL are now prevented by an index-backed constraint. Existing tables are migrated automatically.
- Every MCP tool returns a clear error with a correlation ID instead of raw internal detail.
- Relationships can be removed through model-as-code, and deleting an entity can remove its relationships.
- The enrich transform declares its lookup entity, can keep unmatched codes as they are, and reports the lookup as a dependency.
- Record pages show field details in a tooltip instead of under every value.

## Fixed

- Retyping a field no longer silently breaks survivorship. References move to the new field, and a recompute never writes empty columns for a missing field.
- Survivorship writes and displays reference fields correctly.
- Pickers never show a missing field or entity as if it were the first option, and saving is blocked until it is fixed.
- Two entities with the same name in different domains no longer break schema changes for the whole store.
- Deleting an effective-dated or versioned entity, and changing its fields, now succeeds.
- Count and aggregate tools apply the same filters as the record query.
- Findings left by quality rules that were withdrawn before upgrading are released automatically.
- A date without a time zone is no longer shifted by the server's time zone when used as an effective date.

## Security

- Updated a CBOR library for a denial-of-service advisory.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.7.0) — `primodel-7.7.0-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.7.0
```

## v7.6.0 — 2026-11-11

## Breaking

- Range rules on date fields take ISO dates (for example 1920-01-01). A bare year is rejected.

## New

- Effective-dated and versioned entities get generated query functions in the canonical database (as-of, current, periods or versions, and active-or-latest), usable from SQL sources, data products and table functions.
- References to effective-dated and versioned entities resolve to the version in force now, or else the last one that was in force, never a future one.
- Every data domain has a time zone, editable on the domain page and in model-as-code. It defines "today" for effective-dated data. Existing domains default to UTC.
- Field impact analysis shows which pipelines, data products, webhooks, quality rules and references a field change affects, in the field dialogs, the deploy review and the MCP tools.
- The pipelines list has search, filters, grouping and sorting, with views you can share by URL.
- A field's classification is kept at least as high as its sensitivity tags require. A Classification alignment page lists and fixes any discrepancies.
- A normalize-roman-alphabet pipeline operator and a matching database function fold accented and special Latin letters to plain ASCII, with identical results in both.
- An MCP tool lists the classification levels, sensitivity tags and compliance frameworks that fields accept.
- An MCP tool recomputes a golden entity on demand, and another releases the findings of a withdrawn quality rule.

## Improved

- Creating a survivorship configuration provisions its recompute pipeline and fills the golden entity right away, even when the source is already loaded.
- MCP tools accept a field's name as well as its ID.
- The data quality dashboard shows the current state, with blocked and flagged rows reported separately. Flagged rows are marked in the entity's data view.
- Emptying a large entity is much faster.
- The dark theme's tertiary text is easier to read.

## Fixed

- Records whose key includes a date, number or other non-text column open correctly.
- Opening an entity page no longer records a denied lake configuration request for domain owners.
- Survivorship works when the source and golden entities live in different domains.
- Range and pattern quality rules on date fields evaluate correctly. A rule that can't be evaluated against its field's type is refused instead of silently passing.
- Quality-rule findings are released when the rule is withdrawn or a newer version finds the rows clean.
- Golden-record recomputes no longer leave two current versions of a record.
- Unknown compliance framework names are rejected with the list of valid ones.
- The bronze export warning is shown as a plain notice while bronze export is off.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.6.0) — `primodel-7.6.0-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.6.0
```

## v7.5.0 — 2026-11-10

## Breaking

- Effective-dated entities created before this release must be converted once (the "converge effective-from" action) before they can ingest again; the conversion also updates the pipelines that feed them.
- A unique constraint is now refused on versioned and effective-dated entities, where every version repeats the value.

## New

- Effective-dated entities keep their period in platform-managed "effective from" and "effective until" columns, and an empty start or end means open-ended.
- Effective-dated settings can be expressed in model-as-code and through the MCP tools.
- Changing a pipeline's source tag offers to relabel the rows it already wrote.
- A value-based Referential data-quality rule checks that a field's value exists in another entity, and re-checks when the other entity changes.
- Cross-field data-quality rules can compare dates and text.
- Data-quality rules are evaluated against existing rows when they are created, activated or changed.
- An MCP tool sets classification and sensitivity on existing entities and fields.
- Owners can empty an entity of all its rows.

## Improved

- The data-quality rule list hides superseded and retired rules by default, with a toggle to show them.
- Model-as-code reports attribute changes it cannot apply to an existing entity instead of ignoring them, and picks up display-name renames.
- Lake tables are now named per domain; run a one-time re-export, after which the old tables can be deleted.

## Fixed

- A stored-credential reference that cannot be resolved now fails the request instead of sending it unauthenticated.
- Stored secrets read back consistently across pipelines.
- The OAuth2 grant type is chosen from a list instead of typed by hand.
- Turning multi-source on or off no longer clears field classification, sensitivity tags or unique flags.
- Profiling works on entities with uuid columns.
- The hierarchy view no longer marks a self-reference as broken when the parent exists.
- A diagram shows a newly added existing entity without a reload.
- Filter bar layout on hierarchical tables, and a double scrollbar.
- SQL sources over the canonical store accept regular expressions.
- An offset timestamp mapped into a date field no longer lands a day early.
- Lake commits that are retried no longer leave orphaned files, and the ClickHouse query-back is reliable.
- Schema changes made on one node are picked up by every node.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.5.0) — `primodel-7.5.0-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.5.0
```

## v7.4.3 — 2026-11-09

## New

- Field mappings can target date fields as Date, keeping the calendar date exactly as written.

## Improved

- Pipeline settings errors name the setting and list the accepted values, and pipeline validation catches every error that saving would.
- Slow database connections report a timeout instead of suggesting a TLS problem, and Db2 gets more time to start.
- The runs summary counts runs that are stuck without being tracked.
- Empty data views show a placeholder that says whether filters are the reason.

## Fixed

- A value a field mapping cannot convert is now quarantined with a reason instead of disappearing, and a run that loses records fails instead of reporting success.
- A snapshot run that lost records no longer deletes existing rows.
- Text values that look like dates are stored exactly as received.
- SQL sources reading date columns no longer produce an unreadable placeholder value.
- Connections configured to allow unencrypted traffic are now honoured when testing and running pipelines.
- Profiling an entity with yes/no fields works.
- Filtering records on an empty value finds empty values.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.4.3) — `primodel-7.4.3-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.4.3
```

## v7.4.2 — 2026-11-09

## New

- Field mappings can set a target field to a constant value.

## Improved

- The runs summary counts runs that are stuck without a queued message separately.

## Fixed

- An HTTP step that uses a stored credential now authenticates with it when tested, and the form no longer asks for the inline fields alongside it.
- A field-mapping step with a misspelled or missing operator argument is now rejected with a message naming it, instead of silently writing an empty value.
- Agents creating entities can set each field's classification and sensitivity tags, and see them when describing fields.
- Buttons on the emergency access page no longer stretch across the page.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.4.2) — `primodel-7.4.2-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.4.2
```

## v7.4.1 — 2026-11-09

## New

- Model files can name an entity's hierarchy parent field.
- Ingestion runs left without a queued message are marked failed automatically, and a run can be terminated by hand from the run view.

## Improved

- Model files with an unknown key are rejected with the key's location, and model validation errors explain what is wrong.

## Fixed

- Ingestion into deployments that use S3 object storage no longer fails before writing any rows.
- An ingestion error that retrying cannot fix now fails the run immediately instead of being retried.
- Renaming an entity's physical name now renames its table in place, keeping its data.
- The field-mapping step in the pipeline editor shows field names instead of identifiers.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.4.1) — `primodel-7.4.1-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.4.1
```

## v7.4.0 — 2026-11-09

## New

- HTTP pipelines send a default `User-Agent: Primodel` header, so firewalls that reject requests without one let them through; set the header yourself to override it, or leave it blank to send none.

## Improved

- Credential use grants are chosen by domain name.
- Expired MCP sign-in codes and tokens, and MCP clients unused for 90 days, are cleaned up automatically.

## Fixed

- A credential granted to a domain now appears in the pipeline editor's credential picker for that domain's pipelines.
- JSON Lines files no longer fail to ingest when the storage connection delivers a record in pieces.
- An ingestion run whose data cannot be read now fails with the error instead of appearing stuck; temporary faults are retried a limited number of times (`PRIMODEL_INGEST_MAX_DELIVERY_ATTEMPTS`, default 5).
- Layout of the entity dashboard's field list and of system field names on the model canvas.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.4.0) — `primodel-7.4.0-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.4.0
```

## v7.3.2 — 2026-11-09

## Improved

- The MCP sign-in consent page shows where access will be sent, so you can tell a local app from a website before you allow it.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.3.2) — `primodel-7.3.2-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.3.2
```

## v7.3.1 — 2026-11-08

Maintenance release.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.3.1) — `primodel-7.3.1-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.3.1
```

## v7.3.0 — 2026-11-08

## New

- System administrators can monitor the work queue in Primodel (queue depth per shard and worker, backpressure per table), and autoscalers such as KEDA can scale workers on the number of shards under backpressure via `/health/work-queue`, which can be restricted to a separate management port or an address allowlist.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.3.0) — `primodel-7.3.0-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.3.0
```

## v7.2.1 — 2026-11-08

Maintenance release.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.2.1) — `primodel-7.2.1-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.2.1
```

## v7.1.4 — 2026-11-07

## Fixed

- Several Primodel instances starting at the same time against a new database no longer crash while preparing the database or race to create the first administrator.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.1.4) — `primodel-7.1.4-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.1.4
```

## v7.1.3 — 2026-11-04

## Fixed

- When MCP client registration is disabled, Primodel no longer advertises it and explains the refusal, and the MCP token endpoint answers malformed requests with 400 instead of 500.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.1.3) — `primodel-7.1.3-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.1.3
```

## v7.1.2 — 2026-11-04

## Fixed

- Every Primodel pod now loads the plugins bundled in its image, including pods started after the plugins were installed, so Kubernetes deployments with per-pod storage no longer come up without drivers.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.1.2) — `primodel-7.1.2-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.1.2
```

## v7.1.1 — 2026-11-04

**Fixed**
- A connection test against a server that never completes a TLS handshake now fails within a bounded, configurable time (15 seconds by default — set `PRIMODEL_CONNECTION_TIMEOUT_SECONDS` to change it) with a clear message, instead of hanging. The same bound applies when a pipeline opens the connection.
- The enterprise demo seed (`PRIMODEL_DEMO_ENTERPRISE=true`) now creates its Db2 and Oracle connections with TLS disabled (the audited plaintext opt-out), matching the demo containers, which listen in plaintext.
- **Existing installs**: if you registered a Db2 or Oracle connection before TLS became the default for these engines and it now fails to connect, either enable TLS on the server, or open the connection's settings and turn on the plaintext opt-out — the same toggle SQL Server's self-signed demo certificate already uses. No migration step is required; this only affects connections that have not been reconfigured since the default changed.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.1.1) — `primodel-7.1.1-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.1.1
```

## v7.1.0 — 2026-11-03

## New

- Primodel can authenticate to NATS with a username and password, token, creds file or NKey, connect over TLS with your own certificate authority and client certificates, and prefix its NATS streams so several environments can share one broker.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.1.0) — `primodel-7.1.0-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.1.0
```

## v7.0.1 — 2026-11-03

## Security

- Updated the bundled .NET runtime libraries and database drivers to their latest patch releases.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.0.1) — `primodel-7.0.1-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.0.1
```

## v7.0.0 — 2026-10-31

## Breaking

- Plugins built for SDK 2.x no longer load; install the current plugin releases, which are built for this version.

## Improved

- Extension workers can no longer write records directly; data enters only through governed pipelines.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v7.0.0) — `primodel-7.0.0-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:7.0.0
```

## v6.4.0 — 2026-10-31

## Breaking

- When a paid licence expires, existing pipelines and data keep running, but creating new pipelines or entities pauses during a twelve-month Transition Period (Enterprise keeps creating within its limits); versions released after that period won't start under the expired licence.

## New

- The free Community edition is limited to ten entities, alongside three pipelines.
- Demo installations show a banner stating they are not for commercial or production use.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v6.4.0) — `primodel-6.4.0-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:6.4.0
```

## v6.3.0 — 2026-10-30

**New**
- Golden records emit change events like every other entity, so GraphQL subscriptions on a golden entity see merges and removals, labelled by the same change-event rules.
- Change events can carry a business label (for example Joiner, Mover or Leaver) defined by per-entity rules, with a live test that shows the exact event that would be emitted.
- Local accounts carry standard claims and directory attributes (department, cost center, country and more) that row policies can use.

**Security**
- Signing out and in as another user in the same browser tab no longer briefly shows the previous user's data.
- A schema steward can no longer change an entity that belongs to a domain they do not steward.

**Improved**
- Row policies can only use claims that are forwarded to row security, and the allowlist suggests the claims your users actually carry.
- Row-policy history shows what changed in each version and can restore an earlier one, and an approval shows exactly what is being approved.
- System administrators can view every entity's structure, operational status and rule definitions, read-only, without access to its data.
- When single sign-on is configured, the login screen offers it first.
- Errors from authored SQL in table functions and data products show a clear message instead of a generic failure.

**Fixed**
- Saving a diagram that includes entities from several data stores now saves changes on every store, and a relationship between entities on different stores can be created in a single save.
- Saving a schema where a relationship is resent unchanged no longer fails.
- Golden records with more than about 50 fields are now merged by survivorship.
- A golden record is removed once none of its sources has the record any more, and a deleted source record no longer contributes to the golden record.
- After an upgrade, browsers load the new interface instead of a cached old one.
- Removing a relationship between two entities in a single schema save no longer fails.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v6.3.0) — `primodel-6.3.0-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:6.3.0
```

## v6.2.0 — 2026-10-25

**New**
- Data lake export is now governed: a central clearance level and audience control exactly what leaves to the lake. Fields above the clearance are omitted from the lake schema entirely — never masked, never sent as null.
- Per-entity controls for lake export: a domain Owner can enable "silver" (processed) and "bronze" (raw) export separately. Enabling raw export requires the operator's own clearance to cover the entity's most sensitive field, and shows a warning that raw sensitive data will leave in clear text.
- Row-level security is now applied to lake exports: only rows the lake audience is permitted to see are written, and a row that falls outside the audience is removed from the lake.
- Disabling raw ("bronze") export purges what was already captured. Changing the clearance, audience, or a per-entity toggle automatically evolves the lake schema and data to match.

**Improved**
- The whole interface now uses one consistent design system, with aligned forms, one Save per section and consistent spacing in light and dark mode.
- Controls you are not allowed to use are shown read-only with the reason, instead of being hidden or failing when you save.
- The source variants view handles many sources and fields, with sticky headers, a field filter and a "differences only" toggle; "View sources" on a golden record opens it directly.
- Entities are now addressed in URLs by their stable technical name (for example `/demo/hr/person`), so renaming an entity, domain or data store no longer breaks integrations. Existing display-name URLs keep working but are deprecated.
- Settings are reorganised into sections with one Save per section, and unsaved changes are flagged before you leave a section. Secrets such as API keys and webhooks are handled the same way everywhere, and unset settings show their default value.
- Starting a domain migration first shows the pre-flight result, and the button is disabled while a migration for that domain is running.

**Security**
- The container image's operating-system packages are updated, including the fix for CVE-2026-85091 in zlib.

**Fixed**
- Fixed schema changes being applied as database commands (DDL) against a table that lives on a different data store than the one being changed — this could break schema updates for entities that reference across two canonical stores (e.g., a Postgres store and a SQL Server store).
- A failed domain migration now removes what it copied to the target store and can be retried, and the reason a migration stops before switching is shown.
- Saving notification email recipients no longer removes a stored Slack webhook.
- Resizing a column in a data grid no longer re-sorts it.
- The login screen no longer renders as a narrow column.

**SBOM:** download from the [release page](https://github.com/primodel/releases/releases/tag/v6.2.0) — `primodel-6.2.0-linux-amd64.spdx.json` · `linux-arm64` · combined.

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:6.2.0
```

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
