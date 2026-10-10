# MemCastle integration module template

This repository creates one agent integration module independently of its containing plugin.
The initial example targets OpenCode and does not install itself; the module's containing plugin must already be installed.

```sh
git tpl --json questions https://github.com/memcastle/memcastle-integration.tpl
git tpl init https://github.com/memcastle/memcastle-integration.tpl my-integration --init --answer module_name=my-integration --defaults --strict-answers --json
```

The example module runs only agent-side lifecycle glue; all memory operations belong to MemCastle over HTTP/MCP.
Adding another agent kind means implementing its installation adapter and using its own manifest, not a mining source.
