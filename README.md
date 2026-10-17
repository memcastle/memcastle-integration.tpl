# MemCastle integration module template

This repository creates one agent integration module independently of its containing plugin.
The initial example targets OpenCode and does not install itself; the module's containing plugin must already be installed.

```sh
git tpl --json questions "$PWD"
git tpl init "$PWD" ../my-integration --init --answer module_name=my-integration --defaults --strict-answers --json
```

Use `https://github.com/memcastle/memcastle-integration.tpl` for a project shared beyond this machine;
GitTPL keeps the source location selected at init and does not replace a local path automatically.

The example module runs only agent-side lifecycle glue; all memory operations belong to MemCastle over HTTP/MCP.
Adding another agent kind means implementing its installation adapter and using its own manifest, not a mining source.
`git tpl test` checks standalone and nested renders; template CI checks a standalone manifest and entry.
The standalone case also runs the generated Bun formatting, lint, test and build commands without Python.
Nested modules render `INTEGRATION.md`, avoiding a collision with a source module's `README.md` when both typed
modules share an ID and directory; standalone integrations retain their root `README.md`.
