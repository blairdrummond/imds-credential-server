# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.3](https://github.com/blairdrummond/imds-credential-server/compare/v1.0.2...v1.0.3) (2025-11-18)


### Bug Fixes

* fix a thing ([ff7004c](https://github.com/blairdrummond/imds-credential-server/commit/ff7004c789ff16934c885a66035f919275d4363b))
* fix a thing ([fa51d09](https://github.com/blairdrummond/imds-credential-server/commit/fa51d090b5179729fc792aa5ae32ab5a84c67ba7))

## [1.0.2](https://github.com/blairdrummond/imds-credential-server/compare/v1.0.1...v1.0.2) (2025-11-18)


### Bug Fixes

* fix a thing ([6e38343](https://github.com/blairdrummond/imds-credential-server/commit/6e38343156d1fb9082f49633e0e342cd14e0b59a))

## [1.0.1](https://github.com/blairdrummond/imds-credential-server/compare/v1.0.0...v1.0.1) (2025-11-18)


### Bug Fixes

* note license ([0c80ba9](https://github.com/blairdrummond/imds-credential-server/commit/0c80ba918f5db3f4945afd5a9ab4ce39ae50c7e2))
* re-add release-please ([2b9c632](https://github.com/blairdrummond/imds-credential-server/commit/2b9c6328c27e28a7f5443a08981471c51db875d5))

## 1.0.0 (2025-11-18)


### Features

* add ko build ([4094c78](https://github.com/blairdrummond/imds-credential-server/commit/4094c7832ea21dfe7aaaacb4ea93ca86e90e1b2d))


### Bug Fixes

* re-add release-please ([d0ecf7f](https://github.com/blairdrummond/imds-credential-server/commit/d0ecf7f9d3a5cc803ba8c5f8ffa5a74aaf2aa6d8))
* re-add release-please ([ffee760](https://github.com/blairdrummond/imds-credential-server/commit/ffee760637d98fd14411dbc6364e1c607e43ddfe))
* remove sts dependency ([b828c7f](https://github.com/blairdrummond/imds-credential-server/commit/b828c7f359e57fc90a242e09fed561ed6f225b0f))
* update deps ([e29b533](https://github.com/blairdrummond/imds-credential-server/commit/e29b5333d4f346c10e5c0dcdc4c030c86245efbf))

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
