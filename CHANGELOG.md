# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

<<<<<<< HEAD
## [2.1.0] - 2024-04-20

### Added

- The `skip` input to skip on the callee's side of a `worfklow_call`. Otherwise, when the workflow is skipped from
  the caller's side (with an `if` expression), the check path when the workflow was run is not the same as when
  it was skipped ( `outer / inner` vs. `outer` when skipped) !

## [2.0.0] - 2024-01-18

### Removed

- The legacy file exporting the workflow. Now the workflow is only accessible at `.github/workflows/workflow.yml`.

## [1.1.1] - 2024-01-18

### Fixed

- Commit the new workflow to the repository.

## [1.1.0] - 2024-01-18

### Added

- A duplicate of the reusable workflow at the `.github/workflows/workflow.yml`. This is part of a change to have
  every reusable workflow exported under the same conventional path.

## [1.0.0] - 2024-01-07
=======
## [1.0.0] - 2024-05-01
>>>>>>> template/master

### Added

- First release!

<<<<<<< HEAD
[2.1.0]: https://github.com/infrastructure-blocks/docker-compose-metadata-workflow/compare/v2.0.0...v2.1.0
[2.0.0]: https://github.com/infrastructure-blocks/docker-compose-metadata-workflow/compare/v1.1.1...v2.0.0
[1.1.1]: https://github.com/infrastructure-blocks/docker-compose-metadata-workflow/compare/v1.1.0...v1.1.1
[1.1.0]: https://github.com/infrastructure-blocks/docker-compose-metadata-workflow/compare/v1.0.0...v1.1.0
[1.0.0]: https://github.com/infrastructure-blocks/docker-compose-metadata-workflow/releases/tag/v1.0.0
=======
[1.0.0]: https://github.com/infrastructure-blocks/github-actions-workflow-template/releases/tag/v0.1.0
>>>>>>> template/master
