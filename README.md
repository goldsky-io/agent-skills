# Goldsky Agent Skills

Workflow-based AI skills for the Goldsky CLI and Turbo pipelines. These skills guide AI assistants through complex blockchain data tasks like deploying pipelines, managing secrets, and debugging issues.

## Supported Tools

These skills work with AI assistants that support the SKILL.md format:

- **Claude Code** - Copy skills to `.claude/skills/` in your project
- **Cursor** - Copy skills to `.cursor/skills/` in your project
- **Other AI IDEs** - Check your tool's documentation for skill/agent support

## Installation

### Manual Installation

Copy the skills you need to your project's skills directory:

```bash
# For Claude Code
cp -r agent-skills/skills/* .claude/skills/

# For Cursor
cp -r agent-skills/skills/* .cursor/skills/
```

Skills are automatically discovered by the AI assistant when placed in the appropriate directory.

## Available Skills

| Skill                 | Description                                            |
| --------------------- | ------------------------------------------------------ |
| `turbo-pipelines`     | Create, configure, and update Turbo pipelines          |
| `turbo-monitor-debug` | Monitor pipelines and debug issues                     |
| `turbo-lifecycle`     | List and delete pipelines                              |
| `goldsky-auth-setup`  | Login, projects, and initial setup                     |
| `goldsky-secrets`     | Manage credentials for sinks (PostgreSQL, Kafka, etc.) |
| `goldsky-datasets`    | Discover available blockchain datasets and chains      |

## Usage

Skills are invoked in your AI assistant's chat interface. You can either:

**1. Invoke by name:**

```
/turbo-pipelines
/goldsky-datasets
```

**2. Describe what you want (natural language):**

> "Help me deploy a pipeline that reads ERC20 transfers from Base and writes to PostgreSQL"

> "What blockchain datasets does Goldsky support?"

> "Create a secret for my ClickHouse database"

**3. Ask for help:**

> "I'm getting an error in my pipeline logs, can you help debug?"

The AI will automatically use the appropriate skill based on your request.

## Prerequisites

- [Goldsky CLI](https://docs.goldsky.com/get-started/cli) installed (`curl https://goldsky.com | sh`)
- Logged in via `goldsky login`
- Turbo CLI extension installed (`curl https://install-turbo.goldsky.com | sh`)

## Skill Structure

Each skill contains:

```
skill-name/
├── SKILL.md           # Main skill instructions
├── templates/         # YAML templates, code snippets (optional)
├── scripts/           # Helper scripts (optional)
└── data/              # Reference data, schemas (optional)
```

## Documentation

- [Goldsky Docs](https://docs.goldsky.com)
- [Turbo Pipelines Guide](https://docs.goldsky.com/turbo-pipelines/introduction)
- [CLI Reference](https://docs.goldsky.com/turbo-pipelines/cli)

## License

MIT
