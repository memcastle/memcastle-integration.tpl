# MemCastle integration module template

This repository creates one agent integration module independently of its containing plugin.
The initial example targets OpenCode and does not install itself; the module's containing plugin must already be installed.

```sh
git tpl --json questions "$PWD"
git tpl init "$PWD" ../my-integration --init --answer module_name=my-integration --defaults --strict-answers --json
```

After publication, the template URL `https://github.com/memcastle/memcastle-integration.tpl` replaces the local path.

The example module runs only agent-side lifecycle glue; all memory operations belong to MemCastle over HTTP/MCP.
Adding another agent kind means implementing its installation adapter and using its own manifest, not a mining source.
