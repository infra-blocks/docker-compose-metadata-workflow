# docker-compose-metadata-workflow
[![Git Tag Semver From Label](https://github.com/infrastructure-blocks/docker-compose-metadata-workflow/actions/workflows/git-tag-semver-from-label.yml/badge.svg)](https://github.com/infrastructure-blocks/docker-compose-metadata-workflow/actions/workflows/git-tag-semver-from-label.yml)
[![Update From Template](https://github.com/infrastructure-blocks/docker-compose-metadata-workflow/actions/workflows/update-from-template.yml/badge.svg)](https://github.com/infrastructure-blocks/docker-compose-metadata-workflow/actions/workflows/update-from-template.yml)

<<<<<<< HEAD
This reusable workflow parses out metadata from a docker compose file. The output is provided as a JSON
object, so it can be mixed with GitHub Actions fromJSON expression function.
=======
This repository is a template for creating reusable GitHub Actions Workflows. Go through the below checklist
upon instantiating this template:
- Remove the [trigger update from template workflow](.github/workflows/trigger-update-from-template.yml)
- Edit the content of [the placeholder](.github/workflows/workflow.yml) for your reusable workflow.
- Update the status badges:
    - Remove the `Trigger Update From Template` status badge.
    - Add the `Update From Template` status badge.
    - Rename the rest of the links to point to the right repository.
- Edit this document and update the relevant sections
- Prepare the [changelog](CHANGELOG.md) for the first version of the module that will be released.
>>>>>>> template/master

## Inputs

|        Name         | Required | Description                                                                                                                                                                  |
|:-------------------:|:--------:|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| docker-compose-file |  false   | The path to the docker compose file, relative to the git root. Defaults to "docker/docker-compose.yml"                                                                       | 
|        skip         |  false   | A boolean indicating whether to skip the workflow. This is to workaround the required checks discrepancy when the workflow is skipped from the caller. It defaults to false. |

## Secrets

N/A

## Outputs

|   Name   | Description                                           |
|:--------:|-------------------------------------------------------|
| metadata | A stringified JSON object of the docker compose file. |

## Permissions

|  Scope   | Level | Reason                 |
|:--------:|:-----:|------------------------|
| contents | read  | To checkout your code. |

## Concurrency controls

N/A

## Timeouts

N/A

## Usage

```yaml
name: Docker Compose Metadata

on:
  push: ~

jobs:
  docker-compose-metadata:
    permissions:
      contents: read # Needed to check out the project.
    uses: infrastructure-blocks/docker-compose-metadata-workflow/.github/workflows/workflow.yml@v1
    with:
      # Defaults to docker/docker-compose.yml
      docker-compose-file: docker-compose.yaml
  do-something-with-metadata:
    runs-on: ubuntu-22.04
    needs:
      - docker-compose-metadata
    steps:
      - run: |
          echo "The image of service toto is: ${{ fromJson(needs.docker-compose-metadata.outputs.metadata).services.toto.image }}"
```


### Releasing

The releasing is handled at git level with semantic versioning tags. Those are automatically generated and managed
by the [git-tag-semver-from-label-workflow](https://github.com/infrastructure-blocks/git-tag-semver-from-label-workflow).
