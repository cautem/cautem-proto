# cautem-proto

First-party Protocol Buffer contracts and generated clients for cautem modules.
The `cautem.control.v1` schema is the source of truth for Gateway, Go and
Python SDKs, CLI integrations, and the browser client. OpenShell protocol files
remain pinned to their upstream source and are managed by the compatibility
tools in the workspace.

## Generate and validate

Requires Go 1.27.2, Buf 1.66.0, Node.js 22+, and npm.

```sh
go install github.com/bufbuild/buf/cmd/buf@v1.66.0
go mod tidy
npm ci --prefix typescript
buf lint
buf generate --template buf.gen.yaml
buf generate --template typescript/buf.gen.yaml
npm run build --prefix typescript
```

Use `buf breaking --against <previous-schema.binpb>` before changing a released
contract. Generated Go and TypeScript sources are checked in; CI regenerates
them and rejects a diff.

The Go packages are under `gen/go/cautem/control/v1`. The browser package is
`typescript/` (`@cautem/control-client`) and supplies Connect-Web transport and
service clients as well as generated message types.
