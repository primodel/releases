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

- **A cosign signature + SLSA provenance** — a Sigstore (keyless) signature proving the image was
  published by Primodel's GitHub Actions pipeline, plus provenance recording the commit it was built
  from. Verifiable against the **public image**, no source access required.
- **A key-based cosign signature**, from **v3.1.2** onward — verifiable against `primodel.pub` in this
  repository with no network access to Sigstore's transparency log, which is what an air-gapped or
  egress-restricted environment needs. Images before v3.1.2 are keyless-signed only.
- **An SBOM** — the full dependency inventory (NuGet, npm, OS packages) for your vulnerability scanners.

## Verify a release

You only need the public image reference. Replace `<version>` with a tag (e.g. `1.0.0`).

**Signature — prove it's genuinely from Primodel:**

```bash
cosign verify ghcr.io/primodel/primodel:<version> \
  --certificate-identity-regexp '^https://github.com/Wadman-IT/Primodel/\.github/workflows/.*' \
  --certificate-oidc-issuer https://token.actions.githubusercontent.com
```

**Signature, offline — for air-gapped or egress-restricted environments:**

The keyless check above contacts Sigstore's Fulcio and Rekor services. Where that is not possible, verify
against the public key in this repository instead:

```bash
curl -fsSLO https://raw.githubusercontent.com/primodel/releases/main/primodel.pub
cosign verify --key primodel.pub ghcr.io/primodel/primodel:<version>
```

`primodel.pub` is the public half of the release signing key; the private half never leaves the release
pipeline. The same key is also published on the [security page](https://primodel.io/security/), so you can
cross-check the two sources. This applies from **v3.1.2** onward.

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
