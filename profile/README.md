## AI4Paper - Multi-Agent Academic Paper Writing System

### Vision

AI4Paper is an intelligent multi-agent system designed to automate the academic paper writing process. Users provide a research topic, and our system orchestrates multiple specialized AI agents to collaboratively produce high-quality academic papers through a structured, stage-based workflow.

---

### Abstract Architecture

```mermaid
flowchart TB
    subgraph Input
        A[User Input<br/>Topic/Goal]
    end

    subgraph Orchestration
        B[Orchestrator<br/>Main Agent]
        C[Planning Agent<br/>Stage Design & Task Breakdown]
        D[Monitor Agent<br/>Progress Track & Quality Check]
    end

    subgraph TaskAgents [Specialized Task Agents - Parallel Execution]
        E[Literature Agent<br/>Search & Analyze]
        F[Outline Agent<br/>Structure & Organize]
        G[Writing Agents<br/>Parallel Sections]
        H[Review Agent<br/>Edit & Polish]
    end

    subgraph Output
        I[Final Paper]
    end

    A --> B
    B <--> C
    B <--> D
    C --> E & F & G & H
    D -.-> E & F & G & H
    E & F & G & H --> I
```

---

### Core Components

#### 1. Orchestrator (Main Agent)

The central coordinator that manages the entire paper writing workflow:

- Receives user topic/research goal
- Delegates tasks to specialized agents
- Manages inter-agent communication
- Ensures coherent final output

#### 2. Planning Agent

Responsible for strategic planning:

- Analyzes the research topic scope
- Designs the paper structure
- Breaks down work into parallel-executable stages
- Creates task dependencies and timelines

#### 3. Specialized Task Agents (Parallel Execution)

| Agent                | Responsibility                                            |
| -------------------- | --------------------------------------------------------- |
| **Literature Agent** | Search, retrieve, and analyze relevant papers and sources |
| **Outline Agent**    | Create logical paper structure and section organization   |
| **Writing Agents**   | Multiple agents writing different sections in parallel    |
| **Review Agent**     | Edit, refine, and ensure academic quality standards       |

#### 4. Monitor Agent

Quality assurance and progress tracking:

- Tracks completion status of each stage
- Validates output quality at checkpoints
- Handles error recovery and re-execution

---

### Workflow Stages

```mermaid
flowchart LR
    subgraph Stage1 [Stage 1]
        S1[Topic Analysis<br/>& Planning]
    end

    subgraph Stage2 [Stage 2]
        S2[Literature Review<br/>Parallel Search]
    end

    subgraph Stage3 [Stage 3]
        S3[Outline<br/>Generation]
    end

    subgraph Stage4 [Stage 4 - Parallel Writing]
        S4A[Introduction<br/>Agent]
        S4B[Methodology<br/>Agent]
        S4C[Results<br/>Agent]
        S4D[Discussion<br/>Agent]
    end

    subgraph Stage5 [Stage 5]
        S5[Integration<br/>& Review]
    end

    subgraph Stage6 [Stage 6]
        S6[Final Polish<br/>& Export]
    end

    S1 --> S2 --> S3 --> S4A & S4B & S4C & S4D
    S4A & S4B & S4C & S4D --> S5 --> S6
```

---

### Key Features

- **Topic-Driven**: Simply provide a research topic to start
- **Stage-Based Pipeline**: Clear, structured workflow with defined checkpoints
- **Parallel Execution**: Multiple agents work simultaneously on independent tasks
- **Quality Assurance**: Built-in review and refinement at each stage
- **Modular Design**: Easy to extend with new specialized agents

---

### Getting Started

```mermaid
flowchart LR
    A["User Input:<br/>'Machine Learning for<br/>Climate Change Prediction'"] --> B{AI4Paper}
    B --> C["1. Plans paper structure"]
    B --> D["2. Searches literature"]
    B --> E["3. Generates outline"]
    B --> F["4. Writes sections<br/>(parallel)"]
    B --> G["5. Reviews & integrates"]
    B --> H["6. Outputs final paper"]
    
    C --> D --> E --> F --> G --> H
```

---

### Contributing

We welcome contributions to expand our agent ecosystem. See our contribution guidelines for more details.

### License

See [LICENSE](../LICENSE) for details.
