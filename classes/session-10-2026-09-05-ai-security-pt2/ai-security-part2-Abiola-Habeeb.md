# My Notes — Abiola Habeeb

---

## Key Concepts I Learned

This was Part 2 of implementing security for AI, covering **AI Gateway security, guardrails and content safety in Microsoft Foundry, and protecting AI workloads with Microsoft Defender for Cloud**.

- **Three layers of AI defense in depth.** The **traffic layer** (is this caller authenticated, is it within its rate limit, is traffic routed correctly), the **interaction layer** (is the input/output between the user and the model safe and relevant to them), and the **platform layer** (is the cloud resource hosting the AI solution itself properly secured — storage, access rules, authorized users). Each layer needs its own guardrails, and a gap in any one is a way in.
- **Why an AI Gateway matters.** Without one, multiple applications sharing a single API key share fate: if one becomes compromised, effectively all are compromised, since there's no way to isolate blast radius or trace which application did what. A shared key also means no way to track usage per application, and rotating a compromised key breaks every application relying on it at once. **Azure API Management** acts as this AI Gateway — it lets you assign a separate subscription key per application/team, so a compromise or a rotation affects only that one, and you get per-application authentication, rate limiting (TPM/token-per-minute quotas), and audit logging.
- **Rate limits and errors.** A **403** typically signals exhausted or insufficient permission/quota; a **429** signals a temporary rate limit that resets after a period. End users usually never see these directly — the request just appears to hang — but security engineers and the SOC are the ones investigating when a whole team can't get responses because a shared quota was exhausted.
- **Two authentication models for AI Gateway.** **API key authentication** — a static key identifies the caller, but doesn't map to a specific identity, and rotation breaks everything relying on that key. **Microsoft Entra ID token authentication** — the caller has a real identity (often a managed identity) and the Gateway validates the token's signature, expiration, and claims before authorizing; this allows scoping access to specific security groups and is Microsoft's recommended approach over API keys.
- **Securing the gateway perimeter (defense in depth again).** Restrict network access to specific VNets or private endpoints so only authorized groups can reach a given AI solution; use a managed identity for the gateway when it authenticates to backend resources; enable detailed logging (timestamp, token count, caller) for both security investigation and business justification (e.g. renewing a subscription); and use Azure Monitor metrics to watch request volume, rate-limit rejections, and error rates.
- **Detecting anomalies requires a baseline first.** A system can only flag abnormal behavior once it understands what "normal" looks like for that environment — e.g. daily token usage spiking 10x above baseline, unusual off-hours activity, or an error rate exceeding a defined threshold (e.g. 5%) are all signals worth investigating, but only meaningful relative to an established baseline.
- **Guardrails and content safety in Microsoft Foundry.** These protect input and output at the interaction layer, preventing injection of malicious prompts, policy violations, and leakage of harmful or sensitive content. Core safety controls: **Prompt Shields** (detect jailbreak attempts and direct/indirect prompt injection before they reach the model), **content filters** (broad classification — hate, violence, self-harm — suited to large or public-facing workloads), **block lists** (block specific, well-known terms or patterns — e.g. a sensitive project name or a specific term the organization wants to exclude), **protected material detection** (flags proprietary or non-Microsoft content appearing in generated output), and **groundedness detection** (still in preview — evaluates whether a response is actually supported by the source data, flagging fabricated content).
- **Protecting AI workloads with Microsoft Defender for Cloud.** Combines three capabilities: **discovery** (you can't protect what you don't know exists — inventory every AI resource in the environment), **cloud security posture management (CSPM)** (surfaces exposed or misconfigured AI resources and gives recommendations), and **runtime workload protection** (detects active threats such as unusual access patterns, prompt injection or privilege escalation attempts, unauthorized outbound connections, and anomalous API calls). Defender for Cloud captures suspicious prompt evidence for use during investigation, and integrates with Defender XDR for full incident investigation — filtering AI-related incidents, reviewing prompt evidence, assigning and tracking the investigation, and closing it out as a true or false positive.

---

## Lab / Hands-On Work

### What I did


### What happened / Result


### Challenges I faced


---

## My Takeaways

Through this training I now understand that securing an AI solution isn't a single control — it's layered exactly like defense-in-depth for any other system, just applied to traffic, interaction, and platform instead of network, identity, and data. The demo of Azure API Management made the AI Gateway concept concrete: giving each team its own subscription key instead of sharing one means a compromise or a key rotation only affects one application, not the whole environment. The guardrails section clarified something I'd been fuzzy on — content filters are for broad categories (hate, violence) while block lists are for specific, named terms, and Prompt Shields exist specifically to catch a prompt that *looks* legitimate but is actually malicious. Across the whole session, the same idea kept recurring: you can't detect an anomaly, block a bad actor, or investigate an incident on a resource you never discovered or a baseline you never established.

---

## Questions I Still Have

- What's the practical process for rotating a compromised API key when multiple teams depend on it, beyond simply switching to the secondary key temporarily?
- How does groundedness detection actually determine whether a response is "supported" by source data once it's out of preview — what's the underlying mechanism?
- For an organization already using Entra ID token authentication for its AI Gateway, is there ever a legitimate reason to keep API key authentication running in parallel, or should it be fully retired?

---

## Resources I Found Useful

- Bootcamp — Naija AI and Cloud Security (Microsoft Naija Security Usergroup) GitHub
- [Implement Security for AI — learning path](https://learn.microsoft.com/en-us/training/paths/implement-ai-security/)
- [Configure AI Gateway Security in Microsoft Foundry](https://learn.microsoft.com/en-us/training/modules/configure-ai-gateway-security-foundry/)
- [Implement generative AI guardrails in Azure AI Foundry](https://learn.microsoft.com/en-us/training/modules/moderate-content-detect-harm-azure-ai-content-safety-studio)
- [Operationalize AI responsibly with Azure AI Foundry — learning path](https://learn.microsoft.com/en-us/training/paths/operationalize-ai-responsibly)
- [AI Prompt Shield (Microsoft Entra Global Secure Access)](https://learn.microsoft.com/en-us/entra/global-secure-access/how-to-ai-prompt-shield)

---

*Submitted by: Abiola Habeeb · https://github.com/abiolahabeeb*
