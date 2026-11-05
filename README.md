# Markdown Logic plugins for GitHub Copilot

GitHub Copilot plugin packages for [Markdown Logic](https://markdownlogic.com/), version 0.3.3.

| Plugin | Source | Package ZIP |
| --- | --- | --- |
| Markdown Logic Public | [copilot-public](copilot-public/) | [copilot-public-0.3.3.zip](dist/copilot-public-0.3.3.zip) |
| Markdown Logic | [copilot-main](copilot-main/) | [copilot-main-0.3.3.zip](dist/copilot-main-0.3.3.zip) |

The public plugin converts complete supplied Markdown to PDF, DOCX, HTML or EPUB without an account. The authenticated plugin supports team document workflows through browser OAuth. Each source folder includes its own manifest, remote MCP configuration, Skills, setup documentation, and license notices.

Package ZIPs match the corresponding source folders. Verify downloads against [SHA256SUMS](dist/SHA256SUMS):

```sh
cd dist
shasum -a 256 -c SHA256SUMS
```

## Install in GitHub Copilot CLI

Add this repository as a marketplace, then install the profile you want:

```sh
copilot plugin marketplace add Markdown-Logic/mcp-plugin-copilot
copilot plugin install markdown-logic-public@markdown-logic
```

For authenticated team documents, install `markdown-logic@markdown-logic` instead. Each person completes their own browser OAuth flow for the authenticated connection.

You can also install directly from the source folders:

```sh
copilot plugin install Markdown-Logic/mcp-plugin-copilot:copilot-public
# Or, for authenticated team documents:
copilot plugin install Markdown-Logic/mcp-plugin-copilot:copilot-main
```

These packages use the portable Agent Plugins 1.0 format, with `plugin.json` and `mcp.json` at each plugin root and workflow Skills under `skills/`. Use a Copilot CLI version that supports this format. Other Copilot surfaces and organization policies can differ.

## Connections

| Profile | MCP endpoint | Authentication |
| --- | --- | --- |
| Public | `https://markdownlogic.com/mcp` | None |
| Team documents | `https://mcp.markdownlogic.com` | Browser OAuth |

See each source folder's README for setup, capabilities, and limits. Skills provide instructions and grant no additional service access. File saving and interactive UI support depend on the client.

## Distribution

The repository includes a [marketplace catalog](.github/plugin/marketplace.json) for direct discovery and installation after users add this marketplace. See GitHub's [plugin authoring instructions](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/plugins-creating) and [marketplace instructions](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/plugins-marketplace).

Package schemas and local marketplace installation were checked with Copilot CLI 1.0.103. Both MCP configurations and all seven bundled Skills are discovered.

This repository provides community distribution. Publication here does not imply inclusion in a GitHub-curated catalog, provider endorsement, or completed live-client qualification. Live OAuth, tool execution, generated-file saving, and interactive rendering require separate end-to-end checks.

## License and support

The integration files in this repository are licensed under the [MIT License](LICENSE), with the exclusions in [License scope and notices](LICENSE-SCOPE.md).

Support: support@markdownlogic.com · [Privacy](https://markdownlogic.com/privacy) · [Documentation](https://markdownlogic.com/help/en/connect-an-ai-assistant.html)

This 0.3.3 tree is prepared and unpublished. See [current qualification](RELEASE-0.3.3.md); historical host acceptance does not qualify this artifact.
