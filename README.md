# Paprwork-Releases
Public desktop release artifacts and build workflow for Paprwork. Source code
remains private. A signed webhook from the private source repository dispatches
the workflow with a version tag and commit SHA; a read-only Deploy Key checks
out that exact source commit on public GitHub-hosted runners. Source files are
not published to this repository or uploaded as Actions artifacts.

macOS installers are Developer ID signed and notarized. Windows installers may
be unsigned when explicitly approved for release; see each release's notes.

The `release-desktop.yml` workflow requires the `PAPRWORK_SOURCE_DEPLOY_KEY`,
`MACOS_CERTIFICATE`, `MACOS_CERTIFICATE_PASSWORD`, `APPLE_ID`,
`APPLE_APP_SPECIFIC_PASSWORD`, `APPLE_TEAM_ID`, `CLOUDFLARE_API_TOKEN`, and
`CLOUDFLARE_ACCOUNT_ID` Actions secrets. Its default branch is protected.
Only a verified private version tag may publish a release. The historical
`mirror-0.1.7.yml` workflow is pinned to 0.1.7 and does not build source.
