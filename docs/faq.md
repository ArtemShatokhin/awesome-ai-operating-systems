# FAQ

## What is an AI Operating System?

One layer that runs a company's agent work: the agents, their skills, the company's memory, the connectors they call, and a path for finished work to land. Kortix maps those parts to a git repo, sessions on their own computers, and change requests.

## Is AIOS a product or a paper?

Both, in different places. AIOS from agiresearch is a research kernel with a peer-reviewed paper and a public repository. The AIOS, at the-aios.com, is a separate personal framework. Similar names, different projects.

## Are these AI Operating Systems open source?

Several are. Kortix, Xyne, AIOS (agiresearch), Agno AgentOS and Cloudflare OS publish their code, and Builder Methods Agent OS keeps a public repository. Each entry links to its own source, so you can check the terms that apply to the one you pick.

## Can you self-host an AI Operating System?

Yes. Run it on Kortix Cloud, in your VPC, or on your own on-prem network. Self-host is free. Xyne runs on infrastructure the organization controls. Agno AgentOS deploys to containers on your own cloud. The AIOS has no server to host, because it is files on your machine.

## What does an agent OS leave out?

Usually the company. A kernel schedules agents, a spec kit shapes their instructions, and a runtime serves them to other software. None of the three holds the company's memory and configuration as something the company owns, and none decides how finished work lands.

## How do you start with Kortix?

Start with one job the company already pays for. Run `kortix init` to turn a directory into a project, add the agent and the connectors that job needs, then `kortix ship` to check the configuration and bring it live. Add a trigger or Slack once the first job works.
