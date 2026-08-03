# SBOMs

A committed copy of each release's Software Bill of Materials, named by version
(e.g. `1.0.0.spdx.json`), for teams that want a file to archive or feed to a scanner.

The same SBOM is also **attached to the image** in the registry, so you can always pull it directly:

```bash
cosign download sbom ghcr.io/primodel/primodel:<version>
```

Pre-GA: no releases have been published yet.
