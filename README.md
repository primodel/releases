# Primodel — Releases & Supply Chain

Public release notes, **SBOMs**, and **verification** for the Primodel container image. Primodel's source
is not public, but you don't need it: everything required to trust and inventory a release lives here and
alongside the image in the registry.

- **Image:** `ghcr.io/primodel/primodel`
- **Changelog:** [CHANGELOG.md](./CHANGELOG.md)
- **SBOMs:** [`sbom/`](./sbom) (also attached to each image — see below)
- **Docs:** <https://primodel.io/docs/deployment/releases/>

## Every release is signed and inventoried

Each published image is a multi-arch (`linux/amd64` + `linux/arm64`) build carrying:

- **Signed SLSA provenance** — a Sigstore (keyless) attestation proving the image was built by Primodel's
  GitHub Actions pipeline from a specific commit. Verifiable against the **public image**, no source
  access required.
- **An SBOM** — the full dependency inventory (NuGet, npm, OS packages) for your vulnerability scanners.

## Verify a release

You only need the public image reference. Replace `<version>` with a tag (e.g. `1.0.0`).

**Provenance — prove it's genuinely from Primodel:**

```bash
gh attestation verify oci://ghcr.io/primodel/primodel:<version> --repo Wadman-IT/Primodel
```

**SBOM — get the dependency inventory:**

```bash
cosign download sbom ghcr.io/primodel/primodel:<version>
# or, without cosign:
docker buildx imagetools inspect ghcr.io/primodel/primodel:<version> --format '{{ json .SBOM }}'
```

**Inspect the manifest + attached attestations:**

```bash
docker buildx imagetools inspect ghcr.io/primodel/primodel:<version>
```

A copy of each release's SBOM is also committed under [`sbom/`](./sbom) for teams that want a file rather
than a registry pull.

## Reporting

Security issues: **security@wadmanit.se**. Please do not open public issues for vulnerabilities.
