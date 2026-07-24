## AI4Paper — Tools for AI-Assisted Academic Paper Writing

### Vision

AI4Paper builds open-source tools and practical guidance that help researchers move from a topic to a finished paper with AI assistance — from literature search and experiments to drafting, figures, submission, and revision.

---

### Repositories

Together, these repositories provide tools and guidance for the full research-paper lifecycle.

```mermaid
flowchart LR
    subgraph Research [Research Layer]
        MCP[apaper-mcp<br/>MCP server]
    end

    subgraph Authoring [Authoring Layer]
        PLUGIN[apaper-plugin<br/>AI coding agent toolkit]
    end

    subgraph Guidance [Lifecycle Guide]
        BOOK[book<br/>Practical guide]
    end

    MCP --> PLUGIN
    PLUGIN -->|skills| Author((Author))
    BOOK -->|guides| Author
    BOOK -.-> MCP
    BOOK -.-> PLUGIN
```

| Repository | Stack | What it does |
| ---------- | ----- | ------------ |
| [**apaper-mcp**](https://github.com/ai4paper/apaper-mcp) | Bun · TypeScript | MCP server for paper research — searches IACR, DBLP, and Google Scholar; collects BibTeX entries; downloads IACR PDFs. Published as [`@ai4paper/apaper-mcp`](https://www.npmjs.com/package/@ai4paper/apaper-mcp). |
| [**apaper-plugin**](https://github.com/ai4paper/apaper-plugin) | Claude Code · Codex · OpenCode | An academic paper-authoring toolkit for AI coding agents. It bundles `writing` and `creating-figures` skills with the `apaper-mcp` server for literature research, IEEE-style prose, and publication-quality figures. |
| [**book**](https://github.com/ai4paper/book) | Typst | A practical guide to using AI4Paper throughout the full AI/ML paper lifecycle: foundations, setup, problem selection, experiments, data and figures, writing, submission, revision, and post-acceptance work. |

#### How they compose

- **Claude Code:** add the marketplace with `/plugin marketplace add ai4paper/apaper-plugin`, then run `/plugin install apaper-plugin@apaper`. The plugin registers both skills and [`apaper-mcp`](https://github.com/ai4paper/apaper-mcp) automatically.
- **OpenCode:** install the toolkit through its [OCX registry](https://ai4paper.github.io/apaper-plugin) with `ocx registry add https://ai4paper.github.io/apaper-plugin --name apaper`, then `ocx add apaper/apaper`.
- **Codex:** install the skills with `npx skills add ai4paper/apaper-plugin -a codex`, then register the MCP server with `codex mcp add apaper-mcp -- npx -y @ai4paper/apaper-mcp`.
- **Across the paper lifecycle:** follow the [`book`](https://github.com/ai4paper/book) for practical guidance from setting up a project and finding a research problem through experiments, writing, submission, revision, and post-acceptance work.
- **Bring-your-own client:** point any MCP-compatible client at [`apaper-mcp`](https://github.com/ai4paper/apaper-mcp) directly for just the research tools.

---

### Contributing

We welcome contributions across all repos. Open an issue or PR on the relevant repository.

### License

See [LICENSE](../LICENSE) for details.
