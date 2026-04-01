# NewsBlur CLI Skill

An AI skill that teaches your agent every [NewsBlur CLI](https://newsblur.com/features/cli) command. Works with Claude Code, Cursor, Windsurf, and any tool that supports the [Skills standard](https://skills.sh).

## Install

```
npx skills add samuelclay/newsblur-cli-skill
```

The CLI itself must also be installed and authenticated:

```bash
uv pip install newsblur-cli
newsblur auth login
```

## Why use the skill instead of the MCP server?

The [NewsBlur MCP server](https://newsblur.com/features/mcp) returns raw JSON that lands in your agent's context window. A single saved stories query can burn through nearly 40,000 tokens. The skill runs the CLI instead, which returns clean, formatted text. Same query, same results, about a third of the tokens.

In testing, the MCP server used 39,553 tokens for a saved stories query. The same query through the skill used 11,735.

If your tool supports skills, use the skill. If it only supports MCP, use the MCP server.

## What's in the skill

The skill file contains the full command reference: every subcommand, every flag, every output format. Your agent loads it once and can read feeds, search stories, train classifiers, manage subscriptions, and get daily briefings on your behalf.

## Requirements

- [NewsBlur CLI](https://pypi.org/project/newsblur-cli/) (`uv pip install newsblur-cli`)
- Premium Archive ($99/year) or Premium Pro ($29/month) subscription
- OAuth authentication via browser
