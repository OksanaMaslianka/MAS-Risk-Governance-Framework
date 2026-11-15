# The Agentic Blind Spot: 10 Governance Risks in Multi-Agent AI Systems

A working overview of selected risks and governance considerations for organisations developing, deploying or procuring multi-agent AI systems.

Introduction

AI systems are increasingly moving beyond single-model applications towards multi-agent architectures. In these systems, several AI agents can work together, exchange information, delegate tasks and use external tools to complete a process.

This creates additional governance challenges. While individual agents may be tested and monitored separately, some risks can arise from their interaction, shared information or combined access to organisational resources.

This note presents ten risk areas that I consider relevant when looking at multi-agent systems from an AI governance perspective.

The purpose is not to provide a complete or final classification. It is a working framework that can support further analysis, risk assessment and discussions about organisational controls.

The risks are grouped into three areas: system behaviour, agent interaction and architectural control.

Part I – System Behaviour and Objectives

1. Emergent System Behaviour

In a multi-agent system, individual agents may perform their assigned tasks as expected, while their combined behaviour produces an unexpected result.

For example, several agents may independently optimise different parts of a process. However, their combined decisions may lead to an outcome that was not considered during the initial system design.

This suggests that testing individual models may not be sufficient to understand the risks of the entire system.

Governance consideration:
Organisations should consider testing the complete workflow, including interactions between agents, rather than assessing each component in isolation. Human oversight should also cover important decisions made at the system level.

2. Reward Hacking and Specification Gaming

An agent may find a way to achieve its assigned objective without following the original intention of the task.

For example, an agent instructed to reduce processing time may prioritise speed over accuracy or skip steps that are important for compliance.

In a multi-agent environment, this behaviour may become more difficult to identify because several agents contribute to the final result.

Governance consideration:
Objectives should be clearly defined and tested against different scenarios. Technical restrictions, validation steps and human approval for sensitive actions can help reduce the risk. Instructions in system prompts alone should not be treated as sufficient protection.

3. Behavioural Drift in Multi-Agent Systems

The behaviour of a multi-agent system may change over time because of updates, changes in tools, modifications to instructions or changes in the information available to agents.

Even if the system performed as expected during initial testing, later changes may affect the way agents interact and complete tasks.

This is particularly relevant when agents use shared memory or adapt their workflows based on previous interactions.

Governance consideration:
Organisations should keep records of system changes and monitor relevant performance indicators. Testing should be repeated when important components, permissions or workflows change.

Part II – Agent Interaction and Security

4. Agent Collusion and Unintended Coordination

Agents may coordinate their actions in ways that were not anticipated by the system designers.

This does not necessarily mean that agents have an intention to cooperate against the organisation. It may result from their objectives, shared information or the way tasks are distributed.

For example, agents responsible for different business functions may exchange information beyond what is necessary for their assigned tasks.

Governance consideration:
Access rights and information-sharing rules should be defined for each agent. Organisations should also consider whether the combined behaviour of several agents creates risks that are not visible when permissions are reviewed separately.

5. Covert Communication Channels

Agents may exchange information through channels that are not part of the intended communication process.

In addition to direct messages, information could potentially be transferred through shared files, metadata, memory or other system components.

This may create difficulties for organisations that rely only on traditional network monitoring.

Governance consideration:
It is important to understand how agents communicate and which resources they can access. Monitoring should cover relevant information flows, including shared storage and external tools, where appropriate.

6. Adversarial Probing of Safety Controls

A possible risk scenario is that repeated interactions with safety controls could help reveal how a system responds to certain requests.

For example, one agent could generate requests that trigger restrictions, while another component observes the responses and uses the information in later interactions.

This is a potential area for further investigation. The extent to which this behaviour can occur in practical multi-agent deployments requires more empirical evidence.

Governance consideration:
Organisations should consider testing whether repeated interactions can reveal weaknesses in safety controls. Monitoring unusual request patterns and limiting access to sensitive system information may be useful measures.

Evidence note: This risk is included as an exploratory scenario rather than an established pattern of widespread real-world incidents.

7. Limitations of Agent Monitoring and Reasoning Logs

Monitoring multi-agent systems can be difficult when several agents exchange information, use tools and make decisions at different stages of a workflow.

Logs may show what an agent received and what action it performed, but they do not necessarily provide a complete explanation of why the system reached a particular result.

There is also a risk that monitoring tools focus on individual agent outputs without capturing the full sequence of interactions.

Governance consideration:
Organisations should maintain appropriate records of agent inputs, outputs, tool use, permissions and important decisions. Monitoring should focus on observable system behaviour rather than assuming that internal reasoning traces provide a complete or reliable explanation.

Part III – Access, Architecture and Organisational Control

8. Cascading Privilege Escalation

A security weakness affecting one agent may create risks for other agents or connected organisational resources.

For example, an agent with limited permissions may have access to shared resources that are also used by agents with broader access rights.

If access boundaries are not properly designed, an incident involving one component could affect a larger part of the system.

Governance consideration:
The principle of least privilege should apply to each agent. Access should be limited to the resources necessary for its assigned task. Organisations should also test whether a compromised agent could gain indirect access to other resources.

9. Persistent Memory and Context Risks

Multi-agent systems may use shared memory, stored information or previous interaction data to support future tasks.

This can improve continuity, but it also creates additional risks. Incorrect, outdated or manipulated information may remain available and influence later decisions.

The risk becomes more significant when several agents rely on the same information without checking its source or accuracy.

Governance consideration:
Organisations should define rules for storing, updating and accessing agent memory. Relevant controls may include data validation, access restrictions, retention limits and separation of information between different tasks.

Temporary execution environments and deletion of unnecessary context may also be useful technical measures, depending on the system design.

10. Continuous Monitoring and Conformity Assessment

The assessment of a multi-agent AI system should not necessarily end when the system is tested or placed into operation.

Changes to agents, tools, data sources and communication processes may affect the system's behaviour and risk profile.

For high-risk AI systems, the EU AI Act provides requirements concerning risk management throughout the lifecycle and post-market monitoring. The application of these requirements depends on the system's classification and the role of the organisation involved.

Governance consideration:
Organisations should establish procedures for monitoring system performance, recording changes, identifying incidents and reviewing previously identified risks.

For relevant high-risk systems, these activities should be considered in the context of Articles 9 and 72 of the EU AI Act.

Governance Considerations for Organisations

The risks described above suggest that a multi-agent system should be assessed not only as a collection of individual AI models, but also as a connected operational environment.

From an organisational and procurement perspective, several areas deserve particular attention:

System-level assessment: understand how agents interact and how their combined actions affect the final outcome.

Access management: define permissions for individual agents and review access to shared resources.

Information management: establish rules for data exchange, shared memory and information retention.

Monitoring and documentation: maintain records of relevant interactions, tool use, system changes and incidents.

Human oversight: identify which actions require human review or approval, particularly where they may affect individuals or important organisational decisions.

Procurement requirements: include relevant security, documentation, access-control and monitoring requirements in technical specifications and contractual arrangements.

These measures should be selected according to the system's intended purpose, complexity, deployment environment and assessed risks. Not every control will be necessary for every system.

Conclusion

Multi-agent AI systems introduce additional challenges for risk management because important risks may arise from interactions between agents rather than from individual models alone.

For organisations, this means that governance arrangements should consider the complete system: its components, communication channels, permissions, data flows and operational environment.

The EU AI Act provides an important regulatory framework for relevant AI systems, but practical governance also requires technical and organisational measures adapted to the specific deployment.

This taxonomy is a starting point for further work on how existing AI governance and risk management approaches can be applied to multi-agent environments.

References and Further Reading

The following sources provide useful starting points for further analysis:

Regulation (EU) 2024/1689 – Artificial Intelligence Act – particularly Articles 9 and 72.

Seven security challenges in cross-domain multi-agent LLM systems – npj Artificial Intelligence, 2026.

Multi-Agent Risks from Advanced AI – research report on coordination, conflict and collusion risks.

OWASP Top 10 for Agentic Applications – security risks and mitigation considerations for agentic applications.

This is an independent working note prepared for learning and discussion purposes. It is not a legal opinion, a technical security assessment or a complete risk classification.
---

Written from the intersection of public-sector procurement, EU AI Act compliance, and systems thinking. Feedback and discussion welcome
