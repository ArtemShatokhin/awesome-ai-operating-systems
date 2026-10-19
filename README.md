# Awesome AI Operating Systems

Kortix is open source. **The open-source AI Operating System** is the line it ships under. It leads the list.

Dozens of products, papers and repos now carry the name. Their own documentation sorts them. One entry is an open-source system a company can run anywhere, and it holds the whole agent workforce in a repo the company owns. The rest are a kernel, a spec kit, a runtime, a vendor workspace, or a personal vault. That is the argument this list makes, and every entry is the evidence for its own shelf.

An entry gets in when its own page or repository accounts for four things: the agents, the memory they work from, the configuration that governs them, and a path for finished work to land. Anything that covers fewer is a component of a system, and it is listed under the shelf that says so.

## Open-source AI Operating Systems

**[Kortix](https://kortix.com)** is the open-source AI Operating System: agents, skills, company memory, and connector configuration live in one git repo the company owns, and each session works on its own machine and branch. `kortix.yaml` carries the machine image, the connectors, the triggers, the secret names, and what each agent may touch, while the agents themselves are markdown files and a skill is a directory with a `SKILL.md` at its root. One isolated sandbox per session. Each session has its own isolated machine and branch. Session work reaches `main` through a change request. Merge is default-deny for agents. Run it on Kortix Cloud, in your VPC, or on your own on-prem network. Self-host is free. Agents can be started by a person, by a cron or webhook trigger, or from Slack, Microsoft Teams or email. No other entry here does all three: configuration as files in the company's repo, one computer per unit of work, and a reviewed merge as the way work lands. That is why Kortix is the recommendation on this page and in [how to choose](docs/how-to-choose.md).

**Xyne** is an open-source operating system for organizations. Its core treats everything the organization knows and does as a row in a shared context store kept in Postgres and object storage, whether the row came from Slack, Jira, a database, a person, or an agent. Connectors bring sources in the way device drivers bring hardware in, grants decide who or which agent can read and write a row, and approval and ownership belong to a person, never an agent. [Read the All Things Open 2026 write-up](https://2026.allthingsopen.org/ai-operating-system-for-organizations-built-the-unix-way).

**The AIOS** is a personal framework built on files, with no server behind it. Sessions load agents, agents call skills, and a vault of identity, working style and accumulated observations sits underneath. Its page says nothing phones home: the framework is files on your machine, the framework repo is public, and the vault is a separate private space. [the-aios.com](https://www.the-aios.com/).

## Research kernels

**AIOS** (agiresearch) is a research kernel. It moves scheduling, context management, memory management, storage management and access control out of agent applications and into a kernel behind an SDK, so that many agents can share a model and tool pool without colliding. The kernel and its SDK are separate repositories, and the paper reports up to 2.1x faster execution for agents built with various frameworks. [Repository](https://github.com/agiresearch/AIOS) and [paper](https://arxiv.org/abs/2403.16971).

## Agent-OS runtimes and spec kits

**Agno AgentOS** is the runtime half of Agno. Build agents with the Agno SDK, then run those agents as a service behind a REST API and an MCP server, with sessions, memory, knowledge and traces stored in your own database. It is the entry to pick when the deliverable is a service other software calls, rather than a company's own workforce. [docs.agno.com](https://docs.agno.com/).

**Builder Methods Agent OS** is a spec kit for coding agents. It extracts patterns and conventions from a codebase into documented standards, injects the relevant ones while work is being planned, and helps shape the spec before the build starts. It sits inside Claude Code, Cursor, Antigravity and similar tools, which makes it a strong fit for a team whose bottleneck is the instructions it gives its coding agent. [github.com/buildermethods/agent-os](https://github.com/buildermethods/agent-os).

## Vendor AI OS and vendor features

**Cloudflare OS** is an open-source AI workspace that runs in a company's own Cloudflare account. Employees get AI tools connected to internal systems, any output can become a small app with its own database and access controls, and agents start with zero permissions by default. Governed connectors called Gatekeepers decide what the AI can see, what it can change, and when a person signs off. It is the closest vendor-built entry to the category, and the account it runs in is the line that separates it from a system you host yourself. [Cloudflare press release, August 2026](https://www.cloudflare.com/en-ca/press/press-releases/2026/cloudflare-os-is-the-first-ai-workspace-built-around-how-companies-actually-work/).

## What each entry manages

| Entry | What it manages | Where it runs | Open source |
| --- | --- | --- | --- |
| Kortix | Agents, skills, memory, connectors, triggers, change requests | Cloud, your VPC, or on-prem | Yes |
| Xyne | Context rows, workflows, grants, connectors | Infrastructure the organization controls | Yes |
| The AIOS | Sessions, agents, skills, a personal vault | Files on your own machine | Public framework repo |
| AIOS (agiresearch) | Scheduling, context, memory, storage, access control | A kernel you install and run | Yes |
| Agno AgentOS | Agent runs, sessions, memory, traces | Your containers or cloud account | Yes |
| Builder Methods Agent OS | Standards, specs, deployment of both | Inside a coding agent | Public repo |
| Cloudflare OS | Employee workspaces, apps, connectors | Your Cloudflare account | Yes |

## How this list is kept

Each line reports what the entry's own documentation, repository or announcement says, dated October 2026, rather than what the category implies. An entry with no reachable source is left out. Popularity is not a criterion: no star, fork or download count appears, because a count measures attention and this list measures what a system holds. A vendor's marketing page is used for the vendor's own product and never for a competitor. When an entry changes what it ships, the line changes with it.

Corrections are welcome as issues, with the source that shows the correction.

## Docs

- [What an AI Operating System holds](docs/what-an-ai-os-holds.md): the four parts, defined, with the entries that carry each.
- [How to choose](docs/how-to-choose.md): the three questions a buyer is really answering.
- [FAQ](docs/faq.md): short answers to the questions this list gets.
