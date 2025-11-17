# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- Initial release of IMDS Credential Server
- Support for serving AWS credentials via EC2 Instance Metadata Service (IMDS) protocol
- Multi-platform binary releases (Linux, macOS, Windows)
- Container images for linux/amd64 and linux/arm64
- Automated release process using Release-Please
- Container image signing with Cosign
- SBOM generation in SPDX and CycloneDX formats
- GitHub attestations for build provenance
- Integration with GitHub Dependency Graph

### Security
- All container images are signed using keyless signing via Sigstore
- Build provenance attestations for supply chain security
- Software Bill of Materials (SBOM) included with releases

---

*Note: This changelog will be automatically updated by Release-Please based on conventional commit messages.*