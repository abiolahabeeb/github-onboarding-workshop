# My Notes — Abiola Habeeb

---

## Key Concepts I Learned

This was Part 1 of implementing security for AI, focused on **securing AI agent identities across Microsoft Entra, Defender XDR, and Copilot Studio**.

- **Why AI security is different.** AI systems inherit every risk that already exists in the cloud, then add their own on top. Models, prompts, grounding data, and agents create a new attack surface that traditional infrastructure controls were never designed for — new attack techniques (prompt injection, jailbreaking, model manipulation, over-reliance), faster data exposure (generative AI can surface oversharing instantly if permissions aren't correct), sprawling "shadow AI" estates, and runtime blind spots that only dedicated AI threat detection can catch.
- **Why AI agent security specifically matters.** Agents act autonomously — they can invoke tools, read data, and take actions on connected systems in response to a natural language prompt, without a human tracing every step. An agent **is an identity**: it requests its own access token, can be over-privileged, and can be compromised just like a user account. Traditional user-centric controls often miss agents entirely because many agents run on a schedule or in response to an event with no signed-in user. The risk is scoped to the agent: a single compromised agent identity can reach every data source, tool, and downstream resource its permissions allow.
- **Key terms.** **Agent identity** — the directory identity an AI agent authenticates with (its own client ID plus a certificate or managed identity). **Agent identity blueprint** — the configuration that defines an agent and its credentials, and is what Conditional Access can target. **Blast radius** — the scope an agent identity could reach if compromised (permissions, knowledge sources, configuration). **Attack path** — the chain of access that could lead to unauthorized data if an agent identity were compromised.
- **Two access patterns.** **Delegated (on-behalf-of / OBO)** — a signed-in user is present, and the agent acts in that user's context; the user's own permissions constrain what the agent can do, and standard user-targeted Conditional Access (MFA, device compliance) applies. **Autonomous (client credentials)** — the agent authenticates directly with its own credential (certificate or managed identity), with no signed-in user; the token subject is the agent identity itself, so Conditional Access must be **scoped to the agent identity**, not a user. Applying a user-targeted policy to an autonomous agent misses the enforcement point entirely, and vice versa.
- **How an agent gets access (the flow).** The agent requests a token from Microsoft Entra → Conditional Access evaluates the request against real-time signals (context, device, location, risk) → if conditions are met, Entra issues the token (otherwise it's blocked or limited) → the target resource validates the token and authorizes the action.
- **Configuring Conditional Access for agents.** Choose the assignment target (user vs. agent/workload identity), define conditions (location, device state, session risk), set grant/session controls (allow, block, require MFA), and — critically — always test in **report-only mode** before enforcing. For scale, target agents by **attribute** (via the blueprint) rather than by name, so new agents that match the attribute automatically inherit the policy without manual onboarding.
- **Recommended policies for autonomous agents.** Allow only specific approved agents and deny everything else by default; block any agent flagged as high risk from reaching resources; and also cover any user account associated with an agent, not just the agent identity itself.
- **Controlling agent access and lifecycle.** Build every agent with **least privilege** (never over-privilege — that's what turns an incident into a breach), operate under policy (every token request evaluated), **review and recertify** permissions periodically (a role can become stale exactly the way a human's unused permissions do after a team change), and **retire cleanly** — disable credentials and remove access the moment an agent is decommissioned or compromised.
- **Discovering and assessing agents (Defender XDR).** The **AI agent inventory** in the Defender portal surfaces agents operating across the environment (discovery depends on connectors like the Microsoft 365 Hub and Copilot Studio connectors). Assessing **blast radius** means examining permissions (what can it reach), knowledge sources (what data can it read, how sensitive is it), and blueprint configuration (what credentials and tools it's allowed to use). **Attack path analysis** traces how access to one agent identity could chain into unauthorized data or resources — especially where an over-privileged agent connects a low-sensitivity entry point to high-value data.
- **Runtime protection for Copilot Studio agents.** **Microsoft Defender for Cloud Apps** provides real-time inspection of agent activity throughout the "agentic loop," blocking risky actions before they execute. Coverage for Copilot Studio depends on evaluating tool invocations (via Work IQ/MCP for Microsoft 365 Copilot agent invocations); agents using unsupported tools aren't covered. After enabling protection, verify it's working in three places: the **AI agent inventory**, **alerts**, and **advanced hunting**.

---

## Lab / Hands-On Work

### What I did


### What happened / Result


### Challenges I faced


---

## My Takeaways

Through this training I now understand that an AI agent has to be treated exactly like any other identity — arguably with more caution, because it can act autonomously without a human in the loop to catch a mistake. The distinction between delegated and autonomous access patterns is the single most important thing to get right, because scoping a Conditional Access policy to the wrong target (user vs. agent identity) means the policy silently does nothing. The demo's live example — asking an AI coding agent to change a link on a website with one prompt, with no code written by hand — made the "agents act autonomously" risk concrete: the same autonomy that makes agents useful is exactly what makes an over-privileged, compromised agent dangerous. Discovery, least privilege, attribute-based policy scaling, and a real retirement process are the controls that keep that risk contained.

---

## Questions I Still Have

- In practice, how do organizations decide whether a given automation should be built as a delegated agent versus a fully autonomous one, given the very different Conditional Access implications?
- What does the review/recertification cadence for agent permissions typically look like compared to human access reviews?
- For agents that call other agents (agentic loops), how is Conditional Access and blast-radius assessment handled across the whole chain rather than just one agent at a time?

---

## Resources I Found Useful

- Bootcamp — Naija AI and Cloud Security (Microsoft Naija Security Usergroup) GitHub
- [Implement Security for AI — learning path](https://learn.microsoft.com/en-us/training/paths/implement-ai-security/)
- [Microsoft Entra Agent ID documentation](https://learn.microsoft.com/en-us/entra/agent-id/)
- [Microsoft Entra security for AI overview](https://learn.microsoft.com/en-us/entra/agent-id/security-for-ai-overview)
- [Secure AI identity infrastructure with Microsoft Entra — learning path](https://learn.microsoft.com/en-us/training/paths/entra-ai-secure-workloads/)
- [Protect agent identities with Microsoft Entra](https://learn.microsoft.com/en-us/microsoft-agent-365/admin/capabilities-entra)

---

*Submitted by: Abiola Habeeb · https://github.com/abiolahabeeb*
