

[![mcptry](https://mcptry.com/badge/com.mahjonghandbook/mcp)](https://mcptry.com/servers/com.mahjonghandbook/mcp)

[![Official Website](https://img.shields.io/badge/Website-mahjonghandbook.com-blue)](https://mahjonghandbook.com)
[![MCP Registry](https://img.shields.io/badge/MCP_Registry-com.mahjonghandbook%2Fmcp-green)](https://www.mcptry.com/servers/com.mahjonghandbook/mcp)
[![Glama Connector](https://img.shields.io/badge/Glama-Connector-purple)](https://glama.ai/mcp/connectors/com.mahjonghandbook/mcp)

Query American NMJL, Chinese Official MCR (81 Fan) & Japanese Riichi Mahjong scoring rules.

- **Official Workbench**: [https://mahjonghandbook.com](https://mahjonghandbook.com)
- **Remote MCP Endpoint**: `https://mahjonghandbook.com/api/mcp` (`streamable-http`, read-only, no API key required)
- **Public OpenAPI 3.0**: [https://mahjonghandbook.com/openapi.json](https://mahjonghandbook.com/openapi.json)
- **LLM Context**: [https://mahjonghandbook.com/llms.txt](https://mahjonghandbook.com/llms.txt) · [https://mahjonghandbook.com/llms-full.txt](https://mahjonghandbook.com/llms-full.txt)

## Tools Provided (4 Read-Only Tools)

| Tool Name | Summary |
| :--- | :--- |
| `lookup_mahjong_scoring_rules` | Compare high-level regional ruleset structures (tile deck size 136 vs 144 vs 152, hand length, and minimum Fan/point entry thresholds) across American, Chinese MCR, Japanese Riichi, and Hong Kong Mahjong. Do not use for Charleston passing steps, NMJL Joker meld legality, or Riichi Furiten checks. |
| `lookup_american_charleston_sequence` | Retrieve exact pre-game tile passing directions (Right, Across, Left), blind pass rules, and Courtesy Pass negotiation steps prior to the first discard in American Mahjong. |
| `check_nmjl_joker_legality` | Validate whether an American Mahjong Joker tile can legally substitute inside a specific meld size (1 to 6 tiles) and retrieve exposed Joker live-turn swap rules. |
| `check_riichi_furiten_and_yaku` | Evaluate Japanese Riichi Mahjong discard/temporary Furiten Ron restrictions and verify whether a hand satisfies the mandatory 1-Yaku win condition independent of Dora. |

## Connect in 10 Seconds

### Claude Code
```bash
claude mcp add --transport http mahjonghandbook https://mahjonghandbook.com/api/mcp
```

### Cursor / Claude Desktop / Windsurf (`mcp.json`)
```json
{
  "mcpServers": {
    "mahjonghandbook": {
      "type": "streamable-http",
      "url": "https://mahjonghandbook.com/api/mcp"
    }
  }
}
```

### Agent Skill (`skills.sh`)
```bash
npx -y skills@latest add AbigailDavised/mahjonghandbook-mcp -y
```

## License

MIT © [MahjongHandbook](https://mahjonghandbook.com)
