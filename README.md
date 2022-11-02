# gha-docker-helpers
Assortment of docker utility containers for use in MobileCoin GHA workflows.

### How to add an image to this set.

1. Create a directory in the root of the repo with the name of the image you want to build.
1. Place a `Dockerfile` in the directory.
1. Add any additional support files, scripts you need.
1. Add a entry in the `.github/workflows/build-and-publish.yaml` `image` matrix matching the name of the directory.

The GHA automation will use the image directory for docker build context.

### Workflow and automation.

1. PR changes to `main`
1. Merge changes to `main` after approvals.
1. On merge to main GHA will automatically create a series for semver git tags bumping the `patch` by default (`v1`, `v1.0`, `v1.0.0`).
1. On `v*.*.*` tag GHA will automatically create a GH Release with automatic release notes.
1. On `v*.*.*` tag GHA will automatically build docker images with the semver series of tags (`v1`, `v1.0`, `v1.0.0`).

### Bump major/minor tags.

Add `#major`, `#minor` to the commit message to create major/minor releases.
