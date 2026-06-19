# OO Design EEM

An External Epistemic Memory (EEM) for **Object-Oriented Design**, built with [expert-agent-builder](https://github.com/benthomasson/expert-agent-builder). Sourced entirely from Wikipedia (CC BY-SA 4.0).

## What's in this repo

| Component | Count | Description |
|-----------|-------|-------------|
| **Sources** | 56 | Wikipedia articles covering GoF patterns, SOLID principles, core OO concepts, and related design principles |
| **Entries** | 56 | Structured summaries of each source article |
| **Beliefs** | 653 | Verified design claims with dependency tracking across 14 derivation depths |
| **Network** | 770 | Total belief nodes (653 IN, 117 OUT/retracted) |

## Use Cases

### Code Review Agent
Review codebases for OO design pattern usage, SOLID principle adherence, and architectural anti-patterns. The belief network provides traceable justifications — every finding links back to Wikipedia source material.

### Design Consultant Agent
Use as a virtual OO design consultant that provides pattern selection guidance, trade-off analysis, and refactoring recommendations. The belief registry captures nuanced relationships — e.g., when to prefer Strategy over State, why Decorator breaks object identity, how Mediator centralisation risks map to SRP violations.

### Architecture Review Agent
Evaluate system architectures against GoF pattern vocabulary and SOLID principles. The agent can identify which patterns are in play, whether they're well-applied, and where design tensions exist — grounded in 653 verified beliefs rather than generic advice.

### Instructor Agent
Deploy as an OO design instructor that teaches GoF patterns, walks through design decisions, and evaluates architectural choices. The belief network captures not just individual patterns but cross-pattern relationships, classification boundaries, and the composition-over-inheritance paradigm.

### Refactoring Agent
Guide refactoring efforts by identifying which OO patterns apply to existing code structures. The agent knows pattern applicability constraints (e.g., Interpreter for simple grammars only, Flyweight when sharing is significant) and can recommend targeted improvements.

## Quick Start

### Prerequisites

Install the CLI tools using [uv](https://docs.astral.sh/uv/):

```bash
# Install the EEM tools
uv tool install ftl-reasons
uv tool install ftl-expert-build

# Install Claude Code (the AI agent runtime)
npm install -g @anthropic-ai/claude-code
```

This installs the CLI tools: `reasons`, `expert-build`, and `entry`.

### Clone and set up

```bash
git clone git@github.com:EEM-Hub/oo-eem.git
cd oo-eem
```

Sources are included in the repo (Wikipedia content, CC BY-SA 4.0).

### Start Claude Code

```bash
cd oo-eem
claude
```

Claude Code automatically reads the `CLAUDE.md` file in this repo, which configures it as an OO design EEM with access to the belief registry, entries, and knowledge tools.

### Query the EEM

Once inside Claude Code, you can:

```
# Search the knowledge base
> reasons search "observer pattern notification"

# Look up a specific belief
> reasons show observer-vs-pubsub-no-broker

# Trace why a belief holds
> reasons explain abstract-factory-most-principle-dense-pattern

# List beliefs by depth
> reasons list --min-depth 5 --max-depth 10

# Check pipeline status
> expert-build status
```

## Extending the EEM

### Add new sources

Add markdown documents to `sources/`, then run:

```bash
expert-build summarize
expert-build propose-beliefs
expert-build accept-beliefs
```

### Derive new beliefs from existing ones

```bash
expert-build derive-review-repair
```

### Export the network

```bash
reasons export -o network.json
reasons export-markdown -o beliefs.md
```

## Architecture

```
sources/          Wikipedia articles (fetched, CC BY-SA 4.0)
    |
    v
entries/          Structured summaries (LLM-generated)
    |
    v
reasons.db        Belief network with dependency tracking (gitignored)
    |
    v
beliefs.md        Markdown export of all beliefs
network.json      JSON export of the full network
```

The pipeline flows from Wikipedia articles through summarization and belief extraction to a queryable knowledge base. Each belief traces back to its source article. Derived beliefs track their justification chains — `reasons explain <id>` shows the full derivation path. Three cycles of derive-review-repair grew the network from 361 premises to 653 active beliefs across 14 derivation depths.

## Belief Network Statistics

| Metric | Value |
|--------|-------|
| Total nodes | 770 |
| IN (active) | 653 |
| OUT (retracted) | 117 |
| Premises | 323 |
| Derived | 330 |
| Max depth | 14 |
| Sources | 56 Wikipedia articles |

## License

All source content is from [Wikipedia](https://en.wikipedia.org) and licensed under [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/) / [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/). This repository and all derived content is distributed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/). See [ATTRIBUTION.md](ATTRIBUTION.md) for the full list of source articles.
