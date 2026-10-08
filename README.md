# platform-tools

Tools the platform ships to other repos and people. Everything here is versioned, and consumers pin a version.

See [platform-bootstrap](https://github.com/mjbrian/platform-bootstrap) for how this repo fits with the others.

## What lives here

| Path | Purpose | Released as |
| --- | --- | --- |
| `.github/workflows/go-service.yml` | Shared CI for Go services | Tag `go-service-v1` |
| `.github/actions/` | Composite actions used by the workflows | Same tags |
| `cmd/plat/` | Platform CLI | Tag `plat-v*`, Homebrew cask |
| `operators/tenant/` | Tenant operator | Image and chart on GHCR |
| `cmd/lab-mcp/` | MCP server for AI agents | Binary and image |
| `templates/` | Backstage golden path templates | Read from `main` |

## Relates to

- `sample-service` and every new service call the shared workflow.
- `platform-gitops` deploys the operator chart.
- The CLI and MCP server read from Argo CD, OpenCost, and Elasticsearch on the clusters.

## Releasing

Breaking changes get a new major tag, such as `go-service-v2`. Fixes move the existing major tag, so callers get them automatically.
