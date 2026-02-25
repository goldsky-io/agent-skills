# Goldsky Agent Skills

AI skills for streaming real-time blockchain data to your infrastructure. Build, deploy, and debug data pipelines that index onchain events from 20+ chains into PostgreSQL, ClickHouse, Kafka, and more.

## Installation

### Option 1: Claude Code Plugin

Add the Goldsky marketplace and install the plugin:

```
/plugin marketplace add goldsky-io/agent-skills
/plugin install goldsky@goldsky-agent-skills
```

Skills are namespaced as `/goldsky:<skill-name>`:

```
/goldsky:turbo-pipelines
/goldsky:goldsky-datasets
```

### Option 2: Copy Skills Directly

Clone this repo and copy the skills into your project's skills directory. Works with any AI tool that supports the [SKILL.md](https://agentskills.io) format (Claude Code, Cursor, etc.):

```bash
git clone https://github.com/goldsky-io/agent-skills.git

# Claude Code
cp -r agent-skills/skills/* .claude/skills/

# Cursor
cp -r agent-skills/skills/* .cursor/skills/
```

Skills are invoked without a namespace:

```
/turbo-pipelines
/goldsky-datasets
```

## Available Skills

| Skill                 | Description                                            |
| --------------------- | ------------------------------------------------------ |
| `goldsky-auth-setup`  | Install CLI, login, and project setup                  |
| `goldsky-datasets`    | Discover available blockchain datasets and chains      |
| `goldsky-secrets`     | Manage credentials for sinks (PostgreSQL, Kafka, etc.) |
| `turbo-pipelines`     | Create, configure, and update Turbo pipelines          |
| `turbo-lifecycle`     | List, delete, pause, resume, and restart pipelines     |
| `turbo-monitor-debug` | Monitor pipelines and debug issues                     |
| `turbo-architecture`  | Design and architect pipeline data flows               |
| `turbo-transforms`    | Write SQL transforms for pipelines                     |

## Usage

You can invoke skills by name or just describe what you want in natural language:

> "Help me deploy a pipeline that reads ERC20 transfers from Base and writes to PostgreSQL"

> "What blockchain datasets does Goldsky support?"

> "I'm getting an error in my pipeline logs, can you help debug?"

The AI will automatically use the appropriate skill based on your request.

## Prerequisites

**None required!** The skills will guide you through setup if needed.

The `goldsky-auth-setup` skill helps you install the Goldsky CLI, log in, and select a project.

## Documentation

- [Goldsky Docs](https://docs.goldsky.com)
- [Turbo Pipelines Guide](https://docs.goldsky.com/turbo-pipelines/introduction)
- [CLI Reference](https://docs.goldsky.com/turbo-pipelines/cli)

## License

MIT
