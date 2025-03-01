# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [6.0.1] - 2022-07-12
### Fixed
- Container clone from snapshot: only create "temporary" DRBD volume if necessary; remove this temporary DRBD resource when the snapshot gets removed.

## [6.0.0] - 2022-06-28
### Removed
- `redundancy`: The setting was unused since a long time (i.e., when we introduced LINSTOR resource groups). Remove some leftover dead code.
- `controllervm`: Should not be used any longer, please use `drbd-reactor::promoter` to set up a [HA LINSTOR Controller](https://linbit.com/drbd-user-guide/linstor-guide-1_0-en/#s-linstor_ha)

### Changed
- default for `statuscache`: This was set to `0` (i.e., disabled) by default. Enable this cache by default and set it to 1 Minute.
- default for `preferlocal`: Set default to `yes`.

## [5.2.2] - 2021-11-18
### Added
- Support for APIVER10

## [5.2.1] - 2021-07-29
### Added
- Support for APIVER9

## [5.2.0] - 2021-07-08
### Added
- Allow https communication to the API via `apicrt`, `apikey`, `apica`
### Fixed
- UEFI disks on ZFS

## [5.1.6] - 2021-06-17
### Added
- Set User-Agent to `linstor-proxmox/$version`
- Add `statuscache` storage.cfg option

## [5.1.5] - 2021-02-17
### Added
- Support for multiple LINSTOR controllers

## [5.1.4] - 2020-11-19
### Added
- Support for APIVER7/8

## [5.1.3] - 2020-08-31
### Added
- Support for APIVER6

## [5.1.2] - 2020-06-23
### Fixed
- increase debian/changelog

## [5.1.1] - 2020-06-23
### Fixed
- Remove temporary resource after `vzdump` in case of backup via a snapshot.

## [5.1.0] - 2020-06-22
### Added
- Snapshot rollback to the last snapshot
- Backups via snapshots (i.e., snapshot support in `map_volume()`/`activate_volume()`)
