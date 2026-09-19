# My Notes — Abiola Habeeb

---

## Key Concepts I Learned

This was Part 3 of implementing security for AI, covering **the four planes of AI security (workload, agent, data, operations), Microsoft Defender for Cloud for AI, Microsoft Agent 365 governance, and how Copilot's grounding process enforces permissions**.

- **Three layers, later framed as four planes.** Securing AI means answering three questions: is the AI **workload** itself secure, what is the **agent** allowed to do, and what **data** can it access — plus a fourth, **operational**, layer for detecting and responding when something goes wrong. Each layer needs a different control, the same way securing a bank means protecting the building, the staff, and the vault contents together, not any one alone.
- **Six recurring AI risks (old problems in new clothes).** **Prompt injection** (hidden instructions tricking the AI into ignoring its real instructions), **tool misuse** (an authorized tool used in an unintended way, like a company credit card used improperly), **identity abuse** (an agent running with excessive permissions, like a master key instead of a room key), **memory poisoning** (bad information from past interactions corrupting future decisions), **data oversharing** (AI surfacing information technically accessible but never meant to be broadly seen), and **agent sprawl** (forgotten or orphaned agents nobody remembers creating, like a former employee's account still active). The common thread: AI hasn't invented new categories of risk — it has given old security problems (excessive permission, poor governance, unmanaged assets) a new surface to reappear on.
- **Four controls map to the four planes.** **Workload → Defender for Cloud** (discover AI resources, assess posture/configuration, detect runtime threats). **Agent → Agent 365** (observe, govern, and secure agents — the control panel for AI agents as if they were digital employees). **Data → Microsoft Purview / DSPM for AI** (understand what information AI can access and where sensitive data is exposed). **Operations → Defender XDR / Copilot for Security** (investigate incidents, correlate alerts, respond quickly). You can't secure what you haven't discovered, so discovery always comes first.
- **Defender for Cloud for AI works in three steps.** **Discover** (build an inventory of every AI service and model deployment across the subscription — you can't secure an AI project you don't know exists), **assess posture** (CSPM reviews configuration and flags misconfigurations/weaknesses before attackers find them), and **detect at runtime** (cloud workload protection raises alerts on live AI activity, feeding into whatever XDR/SIEM tool is in use). Alert types worth knowing: prompt injection/jailbreak attempts, sensitive data appearing in an AI interaction, suspicious access to AI resources (e.g. a credential used from an unusual location at an unusual hour), and anomalous usage spikes (a sudden, unexplained jump in cost or volume).
- **Microsoft Agent 365 does three jobs.** **Observe** (a registry/inventory of every agent, usage analytics, health monitoring, adoption tracking — directly analogous to an identity inventory but for agents). **Govern** (enterprise governance: ownership assignment, approval workflows, audit readiness, access governance). **Secure** (extends the Microsoft security stack — Conditional Access, identity protection, least privilege, threat detection, and Purview controls like DLP and eDiscovery — to agents specifically).
- **The agent lifecycle mirrors human identity lifecycle.** **Register** (give every agent an accountable owner, just as you would with a company asset), **scope** (grant only the minimum permission the agent's task actually requires — least privilege), **monitor** (watch not just what the agent is supposed to do, but what it's actually doing), **review** (periodically recertify that the agent is still needed and its access still appropriate), and **retire** (deactivate and remove access once an agent has reached end of useful life). This can be automated within Agent 365 once configured.
- **How Copilot enforces permissions — the "grounding" process.** Four steps: (1) **prompt** — the user asks a question; (2) **search** — Copilot searches Microsoft 365 content (SharePoint, Teams, email, OneDrive) relevant to the question, without yet checking who can see what; (3) **trim** — the critical security step, where anything the requesting user doesn't have permission to see is filtered out *before* it reaches the reasoning stage; (4) **reason and answer** — Copilot summarizes and generates a response using only the content that survived the permission check. Copilot does not override or grant new permissions — it can only surface what the user's existing Microsoft 365 permissions already allow them to see. This is why fixing oversharing at the source (SharePoint/file permissions) matters more than any AI-specific control: AI makes existing over-permissioned content easier to *find*, it doesn't create new access.
- **Three underlying data risks that predate AI but AI makes worse.** **Shadow AI** (employees using unapproved AI tools the organization has no visibility into), **overexposure** (files or sites accessible to far more people than intended, so AI surfaces what it's permitted to see, which is too much), and **interaction risk** (users pasting sensitive content — payslips, financial data — directly into a prompt). DSPM for AI (Data Security Posture Management) is the tool that helps discover and address these.
- **Governing multiple AI platforms.** Microsoft Purview's **Data Loss Prevention (DLP)** can create policies restricting which AI platforms staff are allowed to send corporate data to (e.g. permitting Copilot but blocking upload of sensitive data to other AI tools), separate from Conditional Access (which governs identity-based access, not data movement) — the two are complementary, not interchangeable.

---

## Lab / Hands-On Work

### What I did


### What happened / Result


### Challenges I faced


---

## My Takeaways

Through this training I now understand that AI security isn't a single new discipline bolted onto existing security work — it's the same discipline (discover, control access, protect data, monitor and respond) applied to a new class of asset. The clearest idea from the session was the grounding/trim process: Copilot doesn't decide what a user can see, it only respects permissions that already exist in SharePoint, Teams, and OneDrive — which means the real fix for AI oversharing is fixing file and folder permissions at the source, not adding AI-specific restrictions on top of a broken permission model. The agent lifecycle (register, scope, monitor, review, retire) also reframed agents for me as something to manage exactly like employee identities, with an accountable owner and a defined end-of-life, rather than as fire-and-forget automations.

---

## Questions I Still Have

- In practice, how do organizations reconcile a SharePoint site with years of accumulated, loosely-permissioned content before rolling out an AI assistant against it — is there a recommended remediation sequence?
- For agent lifecycle recertification, what cadence does Microsoft recommend for reviewing an agent's scope, compared to typical human access review cycles?
- When DLP blocks a user from pasting sensitive content into an unapproved AI platform, what does that experience look like end-to-end, and how is the attempted violation logged for investigation?

---

## Resources I Found Useful

- Bootcamp — Naija AI and Cloud Security (Microsoft Naija Security Usergroup) GitHub
- [Explore Microsoft Agent 365 — learning path](https://learn.microsoft.com/en-us/training/paths/agent-365-solutions/)
- [Manage and secure Microsoft 365 AI services — learning path](https://learn.microsoft.com/en-us/training/paths/manage-secure-microsoft-365-ai-services/)
- [Use Microsoft Purview to manage data security & compliance for Microsoft Agent 365](https://learn.microsoft.com/en-us/purview/ai-agent-365)
- [Agent Management Essentials for Microsoft 365](https://learn.microsoft.com/en-us/microsoft-365/copilot/agent-essentials/agent-essentials-overview)
- [Security and governance in Microsoft Copilot Studio](https://learn.microsoft.com/en-us/microsoft-copilot-studio/security-and-governance)

---

*Submitted by: Abiola Habeeb · https://github.com/abiolahabeeb*
