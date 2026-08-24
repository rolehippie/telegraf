# Changelog

## [2.3.0](https://github.com/rolehippie/telegraf/compare/v2.2.0...v2.3.0) (2026-08-24)

### Features

* use correct ansible facts and properly create repo and key ([04d062b](https://github.com/rolehippie/telegraf/commit/04d062b21491dfb3922bea86317e4335e68ad3f8))

### Bugfixes

* always usw debian stable main repo for ubuntu >= 20.04 ([7a04b7a](https://github.com/rolehippie/telegraf/commit/7a04b7aa876138de4ee264a4f2e4b05d98be3428))
* properly handle empty defaults ([cc9336c](https://github.com/rolehippie/telegraf/commit/cc9336cb3cbef36dba468d32a577d805d879f5db))
* use correct current repo key ([c6d8d3a](https://github.com/rolehippie/telegraf/commit/c6d8d3abb32beadd7938d7702d6a400b4c92f280))
* use valid docker input options for current version ([af167ef](https://github.com/rolehippie/telegraf/commit/af167efcb142044d39aa861e211801ddcd3ca226))

### Dependencies

* **minor:** update dependency pipx:ansible-doctor to v8.4.0 ([#64](https://github.com/rolehippie/telegraf/issues/64)) ([65bac10](https://github.com/rolehippie/telegraf/commit/65bac106e993367cc53dc0d4534500eef1254e72))
* **minor:** update dependency pipx:ansible-lint to v26.8.0 ([#67](https://github.com/rolehippie/telegraf/issues/67)) ([f0db36f](https://github.com/rolehippie/telegraf/commit/f0db36fbf508d9f154e8fe665791628f06743fe4))
* **minor:** update dependency pipx:molecule to v26.8.0 ([f58dcc6](https://github.com/rolehippie/telegraf/commit/f58dcc6537fbfd832cce2b6f160df818bfbf8565))
* **patch:** update dependency pipx:ansible-core to v2.21.3 ([#65](https://github.com/rolehippie/telegraf/issues/65)) ([4da0e08](https://github.com/rolehippie/telegraf/commit/4da0e084991cc35bdf59c51df121a533336a7d23))
* **patch:** update dependency pre-commit to v4.6.2 ([962b00b](https://github.com/rolehippie/telegraf/commit/962b00b38074952bf969223e9618cdc93665afa1))
* **patch:** update dependency python to v3.14.7 ([#62](https://github.com/rolehippie/telegraf/issues/62)) ([28cc91d](https://github.com/rolehippie/telegraf/commit/28cc91d2235af45ad9a7bddf57dad0484f63334c))

## [2.2.0](https://github.com/rolehippie/telegraf/compare/v2.1.0...v2.2.0) (2026-07-27)

## [2.1.0](https://github.com/rolehippie/telegraf/compare/v2.0.0...v2.1.0) (2025-11-17)


### Features

* apply new repo structure and update linting ([a556848](https://github.com/rolehippie/telegraf/commit/a556848e5deaca41a935eee097c7c6d71b76e7ee))

## [2.0.0](https://github.com/rolehippie/telegraf/compare/v1.1.0...v2.0.0) (2024-02-12)


### Features

* drop support for ubuntu 18.04 ([f427910](https://github.com/rolehippie/telegraf/commit/f427910aa12be05f898403988c50d066ba5448ca))
* used full qualified collection names ([d724799](https://github.com/rolehippie/telegraf/commit/d72479992d7467558bf4a2fb676db65a87202fbf))

## [1.1.0](https://github.com/rolehippie/telegraf/compare/v1.0.0...v1.1.0) (2023-04-17)


### Features

* use unified path for repo key and drop legacy key ([15f6545](https://github.com/rolehippie/telegraf/commit/15f6545b53f11011ac9504eec26b453dd48ca6a7))


### Bugfixes

* use right repo key from documentation ([12993a4](https://github.com/rolehippie/telegraf/commit/12993a4af58c07f49fa765585415bfa0d8eea443))
* use right signing key for repo ([54efff3](https://github.com/rolehippie/telegraf/commit/54efff304330815a1e57b87f649b1016160e3c8f))

## 1.0.0 (2023-01-05)


### Features

* restructure workflows and enable automated releases ([0a76523](https://github.com/rolehippie/telegraf/commit/0a76523015e0cd6044e1faf39cf63a7fe538b2be))
