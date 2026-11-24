# JBang Catalog

This repository publishes a JBang catalog from `jbang-catalog.json`.

## Repository Rules

- Keep aliases in `jbang-catalog.json` valid JSON and use exact, reachable Maven or script URLs.
- Preserve the existing `catalogs` and `aliases` structure.
- Document user-facing aliases in `README.md` when adding or changing one.
- Prefer the JBang Maven coordinate or published runner JAR format already used for MCP aliases.
- For stdio MCP servers, preserve `--quiet` in launch examples to keep standard output protocol-clean.

## Validation

- Parse the catalog: `python3 -m json.tool jbang-catalog.json`
- Review the package: `git diff --stat && git diff`
