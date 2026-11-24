# JBang Catalog

A personal [JBang](https://www.jbang.dev/) catalog maintained by [@jonesbusy](https://github.com/jonesbusy).

## Available aliases

| Alias | Description | Requirements |
| --- | --- | --- |
| `oras-java-mcp` | Read-only stdio MCP server for inspecting OCI registries | Java 21+ |

## Run an alias

```bash
jbang --quiet oras-java-mcp@jonesbusy/jbang-catalog
```

The alias runs the prebuilt Quarkus runner JAR through JBang. Start it as a subprocess when configuring an MCP client.

## MCP client configuration

For clients that launch MCP servers with a command and arguments:

```json
{
  "command": "jbang",
  "args": [
    "--quiet",
    "oras-java-mcp@jonesbusy/jbang-catalog"
  ]
}
```

> [!NOTE]
> MCP stdio servers must not write diagnostic output to standard output. The `--quiet` option is required for clean protocol communication.

You can also launch the published runner directly:

```bash
jbang --quiet io.github.jonesbusy:oras-java-mcp:0.0.1:runner
```

## OCI registry configuration

Pass registry-specific options to the server according to its MCP tools and resources. For a public registry such as Docker Hub, no credentials are normally required.

## Catalog format

Aliases are declared in [`jbang-catalog.json`](jbang-catalog.json). JBang resolves the GitHub repository catalog automatically from the `jbang-catalog` repository name.

## Prerequisites

- [JBang](https://www.jbang.dev/download/) installed and available on `PATH`
- Java 21 or newer
