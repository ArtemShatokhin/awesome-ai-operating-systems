# What an AI Operating System holds

An operating system is judged by what it manages. For a company running agent work, four parts have to be accounted for somewhere: the agents, the memory they work from, the configuration that governs them, and a way for finished work to land. A product that covers one or two of these is a component. A system covers all four, and the entries in the [main list](../README.md) are sorted by which parts they actually hold.

## Agents

An agent is the unit of work: a named role with instructions, a model, a reach into tools and resources, and a way to run for more than one turn. The differences between systems show up in how that unit is defined and how much of it you can read. In Kortix an agent is a markdown file carrying a persona, paired with an entry in `kortix.yaml` that says what it may touch, so the role is text you can diff and review. In Xyne, agents are principals with grants over rows in the context store, which makes reach a database permission rather than a file. In AIOS (agiresearch), agents are applications that call a kernel, and the kernel decides which model, memory and tool each one gets. AgentOS by Agno runs agents you built with its SDK or another framework and exposes them as a service. The AIOS loads named specialists into a session. Cloudflare OS starts every agent with zero permissions and hands it access per task.

## Memory

Memory is what the system knows after the conversation ends. It is the part most often claimed and least often inspectable, so ask three questions of any entry: what is stored, who can read it, and where it lives. Kortix keeps company memory as plain files in the project repo today, which means a remembered fact has an author, a timestamp and a diff like any other change. Xyne stores the organization's context as rows in Postgres and object storage, with grants on each row. Agno AgentOS puts sessions, memory and traces in your own database. AIOS (agiresearch) gives the kernel a memory manager that agents share. The AIOS splits memory into what you wrote about yourself, what the AI observed while working with you, and an intent file that encodes judgment. Cloudflare OS ties knowledge to the company's internal systems and the apps built on them.

Ownership decides whether a memory store is an asset. One you can export in a documented format belongs to the company. One you can only browse inside a vendor's interface is a subscription feature.

## Configuration

Configuration is the governance layer: which agents exist, what each may reach, which models run, which tools are allowed, which secrets are granted, and when a person has to approve an action. This is the layer that decides what a process may do before it starts, which is the job an operating system exists to do.

Kortix states the layer in one place. `kortix.yaml` declares the machine image, connectors and triggers, and secret names and grants. An omitted grant resolves to none. Xyne answers with grants attached to rows, checked whenever a person or an agent reads or writes. Agno AgentOS answers with JWT-based role control and multi-tenant isolation built into the runtime. AIOS (agiresearch) answers with an access-control service inside the kernel. Builder Methods Agent OS answers with standards files that shape what a coding agent is told before it writes anything. Cloudflare OS answers with Gatekeepers, where the owner of each internal system sets what the AI can see and change. The AIOS answers with an intent file that sets autonomy levels and escalation triggers.

## A way for work to land

Finished work needs a destination with a review step, or the system is a very good chat window. The entries differ most here, and the difference is easy to test: ask what happens to the output after the agent stops.

In Kortix, a session commits to its branch and opens a change request against the default branch. Session work reaches `main` through a change request. Merge is default-deny for agents, so a person, or an agent an admin explicitly granted the capability, approves the diff. In Cloudflare OS, output becomes an app a colleague can open, with its own database and access controls. In Agno AgentOS, the result returns through the REST API to the product that called it. In AIOS (agiresearch), the result returns to the application that submitted the task. The AIOS routes a closed session back into the vault. Builder Methods Agent OS improves the instructions and the spec, and the commit still happens in the git host your team already uses. Xyne records the decision as a row with its context, and reconciliation keeps a person in the loop.

A system that holds all four parts gives a company one place to answer "what did the agents do, and who approved it". A component answers a narrower question well, and the list is honest about which is which.
