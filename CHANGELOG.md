## v6.0.0 — 2026-10-12

## [6.0.0](https://github.com/Wadman-IT/Primodel/compare/v5.2.0...v6.0.0) (2026-10-12)


### ⚠ BREAKING CHANGES

* Postgres 18 is the minimum supported version for the metadata and canonical databases. Canonical text comparison becomes case-insensitive; existing tables converge at startup, and tables with keys that differ only by case are reported and left unconverted until resolved.

### Features

* SQL Server as a canonical store, with cross-provider migration ([#368](https://github.com/Wadman-IT/Primodel/issues/368)) ([4f1ab17](https://github.com/Wadman-IT/Primodel/commit/4f1ab17b4b61825c24176a2fa84a34b4f1e54232))

**SBOM:** [`primodel-6.0.0-linux-amd64.spdx.json`](./sbom/primodel-6.0.0-linux-amd64.spdx.json) · [`linux-arm64`](./sbom/primodel-6.0.0-linux-arm64.spdx.json) · [combined](./sbom/primodel-6.0.0.spdx.json)

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:6.0.0
```

## v5.2.0 — 2026-10-11

## [5.2.0](https://github.com/Wadman-IT/Primodel/compare/v5.1.2...v5.2.0) (2026-10-11)


### Features

* accept plugin vendor licences through configuration ([#337](https://github.com/Wadman-IT/Primodel/issues/337)) ([d39012e](https://github.com/Wadman-IT/Primodel/commit/d39012ea56e6f2c4f24b2ee4d426a6cf9f31fedd))

**SBOM:** [`primodel-5.2.0-linux-amd64.spdx.json`](./sbom/primodel-5.2.0-linux-amd64.spdx.json) · [`linux-arm64`](./sbom/primodel-5.2.0-linux-arm64.spdx.json) · [combined](./sbom/primodel-5.2.0.spdx.json)

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:5.2.0
```

## v5.1.2 — 2026-10-10

## [5.1.2](https://github.com/Wadman-IT/Primodel/compare/v5.1.1...v5.1.2) (2026-10-10)


### Bug Fixes

* **demo-seed:** run egress pipelines correctly, roll back fully, and deliver to Oracle ([#327](https://github.com/Wadman-IT/Primodel/issues/327)) ([4318c2a](https://github.com/Wadman-IT/Primodel/commit/4318c2a3a69ec016b112d62f99ae4c9c83580e0d))

**SBOM:** [`primodel-5.1.2-linux-amd64.spdx.json`](./sbom/primodel-5.1.2-linux-amd64.spdx.json) · [`linux-arm64`](./sbom/primodel-5.1.2-linux-arm64.spdx.json) · [combined](./sbom/primodel-5.1.2.spdx.json)

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:5.1.2
```

## v5.1.1 — 2026-10-10

## [5.1.1](https://github.com/Wadman-IT/Primodel/compare/v5.1.0...v5.1.1) (2026-10-10)


### Bug Fixes

* **demo-seed:** deliver the Oracle payee leg in Replace mode ([#292](https://github.com/Wadman-IT/Primodel/issues/292)) ([2c3e269](https://github.com/Wadman-IT/Primodel/commit/2c3e269fd182d038ca1b0b1a585dd588d1cc3d04))
* upgrade every OS package in the image and pin source-map-js to 1.2.2 ([#294](https://github.com/Wadman-IT/Primodel/issues/294)) ([c81b617](https://github.com/Wadman-IT/Primodel/commit/c81b617793f3ce62d666f3b901cfc6b9e6b96462))

**SBOM:** [`primodel-5.1.1-linux-amd64.spdx.json`](./sbom/primodel-5.1.1-linux-amd64.spdx.json) · [`linux-arm64`](./sbom/primodel-5.1.1-linux-arm64.spdx.json) · [combined](./sbom/primodel-5.1.1.spdx.json)

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:5.1.1
```

## v5.1.0 — 2026-10-10

## [5.1.0](https://github.com/Wadman-IT/Primodel/compare/v5.0.2...v5.1.0) (2026-10-07)


### Features

* **demo-seed:** seed the HR egress pipelines and roll back the lake pipeline on failure ([#291](https://github.com/Wadman-IT/Primodel/issues/291)) ([45053b6](https://github.com/Wadman-IT/Primodel/commit/45053b6baf38ba7c8d7f39d0ffb33916cc48f03d))


### Bug Fixes

* apply copilot settings without a restart and separate text around tool calls ([#278](https://github.com/Wadman-IT/Primodel/issues/278)) ([510b04e](https://github.com/Wadman-IT/Primodel/commit/510b04eb097bf4af99d7e9a77d89091ca14097db))
* construct the relationship FK resolver in IngestExecutor ([#288](https://github.com/Wadman-IT/Primodel/issues/288)) ([4945476](https://github.com/Wadman-IT/Primodel/commit/4945476c6ea0d33100b8e29aaee85f6e0334ecf0))
* enforce credential grants and allow credential references for every adapter secret ([#281](https://github.com/Wadman-IT/Primodel/issues/281)) ([9fbf3d9](https://github.com/Wadman-IT/Primodel/commit/9fbf3d954e4316daa30e60bdce23b1c9770eb3e1))
* instrument plugin package install and stabilise its tests under load ([#284](https://github.com/Wadman-IT/Primodel/issues/284)) ([9fcdc49](https://github.com/Wadman-IT/Primodel/commit/9fcdc495726c3d8d3942dcd1ba5e6aa35f137329))
* move to Parquet.Net 6.1 with an allocation-lean string path ([#276](https://github.com/Wadman-IT/Primodel/issues/276)) ([c28222a](https://github.com/Wadman-IT/Primodel/commit/c28222a2143689940a86495d518c06a2b79b50b9))
* offer Upsert in sql-target only for engines that can upsert ([#277](https://github.com/Wadman-IT/Primodel/issues/277)) ([cc7c62c](https://github.com/Wadman-IT/Primodel/commit/cc7c62c704049d7b6822d4f8745f4dace4e2fb58))
* recover a stale governed exec identity credential automatically ([#279](https://github.com/Wadman-IT/Primodel/issues/279)) ([2dfb158](https://github.com/Wadman-IT/Primodel/commit/2dfb1589f99611e00c1534b084f72773bb78f723))
* resolve materialize target columns case-insensitively and deflake the role sweep guard ([#286](https://github.com/Wadman-IT/Primodel/issues/286)) ([a0590a5](https://github.com/Wadman-IT/Primodel/commit/a0590a5aba9d9ff5ac9777ac7a82d399e7c4f203))
* upsert and case-insensitive column matching for sql-target on every engine ([#269](https://github.com/Wadman-IT/Primodel/issues/269)) ([93288e4](https://github.com/Wadman-IT/Primodel/commit/93288e422bd095d8b2504355ddbd0882c59b724f))

**SBOM:** [`primodel-5.1.0-linux-amd64.spdx.json`](./sbom/primodel-5.1.0-linux-amd64.spdx.json) · [`linux-arm64`](./sbom/primodel-5.1.0-linux-arm64.spdx.json) · [combined](./sbom/primodel-5.1.0.spdx.json)

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:5.1.0
```

## v5.0.2 — 2026-10-04

## [5.0.2](https://github.com/Wadman-IT/Primodel/compare/v5.0.1...v5.0.2) (2026-10-04)


### Bug Fixes

* evolve existing silver tables on the REST catalog and re-export on upgrade ([#263](https://github.com/Wadman-IT/Primodel/issues/263)) ([2189576](https://github.com/Wadman-IT/Primodel/commit/2189576e1d869c79ecfd1c0d165add4b5420a48d))

**SBOM:** [`primodel-5.0.2-linux-amd64.spdx.json`](./sbom/primodel-5.0.2-linux-amd64.spdx.json) · [`linux-arm64`](./sbom/primodel-5.0.2-linux-arm64.spdx.json) · [combined](./sbom/primodel-5.0.2.spdx.json)

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:5.0.2
```

## v5.0.1 — 2026-10-04

## [5.0.1](https://github.com/Wadman-IT/Primodel/compare/v5.0.0...v5.0.1) (2026-10-04)


### Bug Fixes

* auto-upgrade bundled plugins so an upgraded install does not strand them ([#259](https://github.com/Wadman-IT/Primodel/issues/259)) ([243ee30](https://github.com/Wadman-IT/Primodel/commit/243ee306890451d5064057cc00995a2ad72b0738))
* expand reference fields and de-dupe rows in silver Iceberg tables ([#252](https://github.com/Wadman-IT/Primodel/issues/252)) ([421f135](https://github.com/Wadman-IT/Primodel/commit/421f13597d645ed3d057d300af553d9fec91df80))
* honour the egress allowlist everywhere and stop secrets following a changed endpoint ([#255](https://github.com/Wadman-IT/Primodel/issues/255)) ([02acacb](https://github.com/Wadman-IT/Primodel/commit/02acacb4a0e6a76cdd1e2d43ce8391c6c3713761))

**SBOM:** [`primodel-5.0.1-linux-amd64.spdx.json`](./sbom/primodel-5.0.1-linux-amd64.spdx.json) · [`linux-arm64`](./sbom/primodel-5.0.1-linux-arm64.spdx.json) · [combined](./sbom/primodel-5.0.1.spdx.json)

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:5.0.1
```

## v5.0.0 — 2026-10-04

## [5.0.0](https://github.com/Wadman-IT/Primodel/compare/v4.0.3...v5.0.0) (2026-10-04)


### ⚠ BREAKING CHANGES

* Data Product materialization is removed from the API and UI, and its columns are dropped. Egress pipelines using the Govern transform now withhold unclassified fields above the ceiling unless explicitly allowed. Plugins built against a different Primodel.Sdk major are refused.

### Refactoring

* route every engine call through the provider seam ([#249](https://github.com/Wadman-IT/Primodel/issues/249)) ([d22742d](https://github.com/Wadman-IT/Primodel/commit/d22742d009ad416fbd29f2857ade75d2b1ce4173))

**SBOM:** [`primodel-5.0.0-linux-amd64.spdx.json`](./sbom/primodel-5.0.0-linux-amd64.spdx.json) · [`linux-arm64`](./sbom/primodel-5.0.0-linux-arm64.spdx.json) · [combined](./sbom/primodel-5.0.0.spdx.json)

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:5.0.0
```

## v4.0.3 — 2026-10-02

## [4.0.3](https://github.com/Wadman-IT/Primodel/compare/v4.0.2...v4.0.3) (2026-10-02)


### Bug Fixes

* raise Primodel image openssl/libssl3t64 floor to 3.0.13-0ubuntu3.16 ([#120](https://github.com/Wadman-IT/Primodel/issues/120)) ([9fe729c](https://github.com/Wadman-IT/Primodel/commit/9fe729c50cef4ea7cc035715d71176d96b3c8542))

**SBOM:** [`primodel-4.0.3-linux-amd64.spdx.json`](./sbom/primodel-4.0.3-linux-amd64.spdx.json) · [`linux-arm64`](./sbom/primodel-4.0.3-linux-arm64.spdx.json) · [combined](./sbom/primodel-4.0.3.spdx.json)

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:4.0.3
```

## v4.0.2 — 2026-10-01

## [4.0.2](https://github.com/Wadman-IT/Primodel/compare/v4.0.1...v4.0.2) (2026-10-01)


### Bug Fixes

* reference mappings, and stop the SPA shell answering for removed API routes ([#117](https://github.com/Wadman-IT/Primodel/issues/117)) ([2ac39bd](https://github.com/Wadman-IT/Primodel/commit/2ac39bdb06eed67a8339a60677ac41b5247f8b6f))

**SBOM:** [`primodel-4.0.2-linux-amd64.spdx.json`](./sbom/primodel-4.0.2-linux-amd64.spdx.json) · [`linux-arm64`](./sbom/primodel-4.0.2-linux-arm64.spdx.json) · [combined](./sbom/primodel-4.0.2.spdx.json)

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:4.0.2
```

## v4.0.1 — 2026-10-01

## [4.0.1](https://github.com/Wadman-IT/Primodel/compare/v4.0.0...v4.0.1) (2026-10-01)


### Bug Fixes

* restore the schema the migration reset silently dropped ([#115](https://github.com/Wadman-IT/Primodel/issues/115)) ([ba1415a](https://github.com/Wadman-IT/Primodel/commit/ba1415a5b98ed5a39da36cff1fe1cdbfecf9e306))

**SBOM:** [`primodel-4.0.1-linux-amd64.spdx.json`](./sbom/primodel-4.0.1-linux-amd64.spdx.json) · [`linux-arm64`](./sbom/primodel-4.0.1-linux-arm64.spdx.json) · [combined](./sbom/primodel-4.0.1.spdx.json)

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:4.0.1
```

## v4.0.0 — 2026-10-01

## [4.0.0](https://github.com/Wadman-IT/Primodel/compare/v3.1.12...v4.0.0) (2026-10-01)


### ⚠ BREAKING CHANGES

* rename the integration concept to pipeline ([#111](https://github.com/Wadman-IT/Primodel/issues/111))

### Features

* rename the integration concept to pipeline ([#111](https://github.com/Wadman-IT/Primodel/issues/111)) ([c4da810](https://github.com/Wadman-IT/Primodel/commit/c4da8109aeaebf5b12cd0c82b4f09b57bb9ec1ca))

**SBOM:** [`primodel-4.0.0-linux-amd64.spdx.json`](./sbom/primodel-4.0.0-linux-amd64.spdx.json) · [`linux-arm64`](./sbom/primodel-4.0.0-linux-arm64.spdx.json) · [combined](./sbom/primodel-4.0.0.spdx.json)

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:4.0.0
```

## v3.1.12 — 2026-10-01

## [3.1.12](https://github.com/Wadman-IT/Primodel/compare/v3.1.11...v3.1.12) (2026-10-01)


### Bug Fixes

* assert the patched curl lands in the image ([#110](https://github.com/Wadman-IT/Primodel/issues/110)) ([72b5083](https://github.com/Wadman-IT/Primodel/commit/72b5083474b4f6a630d227932278a92e8e11e327))
* bump js-yaml to 5.4.2 (GHSA-r3ph-w7gj-g6xm) ([#106](https://github.com/Wadman-IT/Primodel/issues/106)) ([c4ea244](https://github.com/Wadman-IT/Primodel/commit/c4ea244926298519c3b39c3d619ee52fad68f83a))
* clear every remaining vulnerable dependency in app and web ([#108](https://github.com/Wadman-IT/Primodel/issues/108)) ([4cb0bdb](https://github.com/Wadman-IT/Primodel/commit/4cb0bdb5bdb251b9aa8cd8b455416efe7bcc6f78))

**SBOM:** [`primodel-3.1.12-linux-amd64.spdx.json`](./sbom/primodel-3.1.12-linux-amd64.spdx.json) · [`linux-arm64`](./sbom/primodel-3.1.12-linux-arm64.spdx.json) · [combined](./sbom/primodel-3.1.12.spdx.json)

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:3.1.12
```

## v3.1.11 — 2026-09-28

## [3.1.11](https://github.com/Wadman-IT/Primodel/compare/v3.1.10...v3.1.11) (2026-09-28)


### Bug Fixes

* **ci:** check out the repository in the merge job, which two steps already needed ([#102](https://github.com/Wadman-IT/Primodel/issues/102)) ([1f14110](https://github.com/Wadman-IT/Primodel/commit/1f141106ccc8c832ade372b9f3104cbcb22fae37))

**SBOM:** [`primodel-3.1.11-linux-amd64.spdx.json`](./sbom/primodel-3.1.11-linux-amd64.spdx.json) · [`linux-arm64`](./sbom/primodel-3.1.11-linux-arm64.spdx.json) · [combined](./sbom/primodel-3.1.11.spdx.json)

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:3.1.11
```

## v3.1.9 — 2026-09-27

_See release history._

**SBOM:** [`primodel-3.1.9-linux-amd64.spdx.json`](./sbom/primodel-3.1.9-linux-amd64.spdx.json) · [`linux-arm64`](./sbom/primodel-3.1.9-linux-arm64.spdx.json) · [combined](./sbom/primodel-3.1.9.spdx.json)

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:3.1.9
```

## v3.1.8 — 2026-09-27

_See release history._

**SBOM:** [`primodel-3.1.8-linux-amd64.spdx.json`](./sbom/primodel-3.1.8-linux-amd64.spdx.json) · [`linux-arm64`](./sbom/primodel-3.1.8-linux-arm64.spdx.json) · [combined](./sbom/primodel-3.1.8.spdx.json)

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:3.1.8
```

## v3.1.7 — 2026-09-26

_See release history._

**SBOM:** [`primodel-3.1.7-linux-amd64.spdx.json`](./sbom/primodel-3.1.7-linux-amd64.spdx.json) · [`linux-arm64`](./sbom/primodel-3.1.7-linux-arm64.spdx.json) · [combined](./sbom/primodel-3.1.7.spdx.json)

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:3.1.7
```

## v3.1.6 — 2026-09-26

_See release history._

**SBOM:** [`primodel-3.1.6-linux-amd64.spdx.json`](./sbom/primodel-3.1.6-linux-amd64.spdx.json) · [`linux-arm64`](./sbom/primodel-3.1.6-linux-arm64.spdx.json) · [combined](./sbom/primodel-3.1.6.spdx.json)

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:3.1.6
```

## v3.1.5 — 2026-09-26

_See release history._

**SBOM:** [`primodel-3.1.5-linux-amd64.spdx.json`](./sbom/primodel-3.1.5-linux-amd64.spdx.json) · [`linux-arm64`](./sbom/primodel-3.1.5-linux-arm64.spdx.json) · [combined](./sbom/primodel-3.1.5.spdx.json)

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:3.1.5
```

## v3.1.4 — 2026-09-26

_See release history._

**SBOM:** [`primodel-3.1.4-linux-amd64.spdx.json`](./sbom/primodel-3.1.4-linux-amd64.spdx.json) · [`linux-arm64`](./sbom/primodel-3.1.4-linux-arm64.spdx.json) · [combined](./sbom/primodel-3.1.4.spdx.json)

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:3.1.4
```

## v3.1.3 — 2026-09-25

_See release history._

**SBOM:** [`primodel-3.1.3-linux-amd64.spdx.json`](./sbom/primodel-3.1.3-linux-amd64.spdx.json) · [`linux-arm64`](./sbom/primodel-3.1.3-linux-arm64.spdx.json) · [combined](./sbom/primodel-3.1.3.spdx.json)

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:3.1.3
```

## v3.1.3 — 2026-09-25

_See release history._

**SBOM:** [`primodel-3.1.3-linux-amd64.spdx.json`](./sbom/primodel-3.1.3-linux-amd64.spdx.json) · [`linux-arm64`](./sbom/primodel-3.1.3-linux-arm64.spdx.json) · [combined](./sbom/primodel-3.1.3.spdx.json)

**Signing key:** [`primodel.pub`](./primodel.pub) — verify offline (no Fulcio/Rekor access needed):
```
cosign verify --key primodel.pub ghcr.io/primodel/primodel:3.1.3
```

## v3.1.2 — 2026-09-25

_See release history._

**SBOM:** [`primodel-3.1.2-linux-amd64.spdx.json`](./sbom/primodel-3.1.2-linux-amd64.spdx.json) · [`linux-arm64`](./sbom/primodel-3.1.2-linux-arm64.spdx.json) · [combined](./sbom/primodel-3.1.2.spdx.json)

## v3.0.0 — 2026-09-22

_See release history._

**SBOM:** [`sbom/primodel-3.0.0.spdx.json`](./sbom/primodel-3.0.0.spdx.json)

## v2.1.0 — 2026-09-08

_See release history._

**SBOM:** [`sbom/primodel-2.1.0.spdx.json`](./sbom/primodel-2.1.0.spdx.json)

## v2.0.2 — 2026-09-08

_See release history._

**SBOM:** [`sbom/primodel-2.0.2.spdx.json`](./sbom/primodel-2.0.2.spdx.json)

## v2.0.1 — 2026-09-07

_See release history._

**SBOM:** [`sbom/primodel-2.0.1.spdx.json`](./sbom/primodel-2.0.1.spdx.json)

## v1.5.0 — 2026-08-30

_See release history._

**SBOM:** [`sbom/primodel-1.5.0.spdx.json`](./sbom/primodel-1.5.0.spdx.json)

## v1.4.0 — 2026-08-28

_See release history._

**SBOM:** [`sbom/primodel-1.4.0.spdx.json`](./sbom/primodel-1.4.0.spdx.json)

## v1.3.0 — 2026-08-25

_See release history._

**SBOM:** [`sbom/primodel-1.3.0.spdx.json`](./sbom/primodel-1.3.0.spdx.json)

## v1.2.1 — 2026-08-25

_See release history._

**SBOM:** [`sbom/primodel-1.2.1.spdx.json`](./sbom/primodel-1.2.1.spdx.json)

## v1.2.0 — 2026-08-24

_See release history._

**SBOM:** [`sbom/primodel-1.2.0.spdx.json`](./sbom/primodel-1.2.0.spdx.json)

## v1.1.0 — 2026-08-13

_See release history._

**SBOM:** [`sbom/primodel-1.1.0.spdx.json`](./sbom/primodel-1.1.0.spdx.json)

## v1.0.0 — 2026-08-11

_See release history._

**SBOM:** [`sbom/primodel-1.0.0.spdx.json`](./sbom/primodel-1.0.0.spdx.json)

# Changelog

All notable changes to Primodel are documented here. This is the public, source-free changelog for the
`ghcr.io/primodel/primodel` image. The format is based on [Keep a Changelog](https://keepachangelog.com/),
and Primodel aims to follow [Semantic Versioning](https://semver.org/).

<!--
Template for each release:

## [1.0.0] — YYYY-MM-DD

Image: `ghcr.io/primodel/primodel:1.0.0`  ·  SBOM: [sbom/1.0.0.spdx.json](./sbom/1.0.0.spdx.json)

### Added
### Changed
### Fixed
### Security
-->
