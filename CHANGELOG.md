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
