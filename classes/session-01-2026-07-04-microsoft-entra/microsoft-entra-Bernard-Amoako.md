# My Notes — [Bernard Amoako Agyemang]

---

## Key Concepts I Learned

<!-- Write the main ideas covered in today's session -->

1. **Conditional Access Policy Configuration**
	- ***Scope definition*** using named locations (trusted IPs/regions) and targeted cloud apps/resources.
	- ***Conditions applied*** based on sign-in risk, user risk, and network context.
	- ***Deployment strategy***: Enable in **Report-only mode** first, monitor impact via sign-in logs, then switch to **On** after validation.
	   
2. **Authentication Methods in Microsoft Entra ID**
	- ***Multi-Factor Authentication (MFA)*** for layered verification.
	- ***Passwordless options***: Windows Hello, FIDO2 security keys, Passkeys and Microsoft Authenticator app.
	- ***One-time passcodes*** (OTP/TOTP) for temporary access.
	- ***Self-Service Password Reset (SSPR)*** to reduce helpdesk dependency.
	   
3. **Privileged Identity Management (PIM)**
	- ***Assignment types***: Eligible (requires activation) vs. Permanent.
	- ***Just-in-time access*** with approval workflows for oversight.
	- ***Time-bound activation*** with configurable duration and expiration.
	  
4. **Securing API plugins for declarative agents in Microsoft 365 Copilot**
	- Identifying API Security Methods by understanding the two most common ways APIs are secured — ***API keys*** and ***OAuth 2.0***.
	- Designing Secure Integrations between a declarative agent's API plugin and a protected API.

---

## Lab / Hands-On Work

<!-- Describe what you did in the lab. Include steps, commands, or screenshots descriptions -->

### What I did
- **Created an API Plugin**: Set up the plugin definition that allows Microsoft 365 Copilot to communicate with an external API in VS Code.
2. **Configuring Authentication:** Configure the plugin to use either an API key.

### What happened / Result
- An API Plugin for Microsoft 365 Copilot was created.
### Challenges I faced
- I had issues installing the Microsoft 365 Agents Toolkit extension but I was later able to resolve it by uninstalling and installing a newly downloaded VS Code. 

---

## My Takeaways

<!-- What was most valuable to you personally from this session? -->
- I learnt that Layered security combining Conditional Access, modern authentication, and PIM provides comprehensive protection.
- I learnt that Report-only mode is essential for safely validating policy changes before enforcement.
- I gained a clear grasp of why APIs need to be secured and the difference between simple API keys and the more robust OAuth 2.0 framework.

---

## Resources I Found Useful

<!-- Any links, docs, or Microsoft Learn modules you found helpful -->

- YouTube Channel - Microsoft Naija Security User Group 
- Microsoft Learn Module: "Authenticate your API plugin for declarative agents with secure APIs"

---

*Submitted by: [Bernard Amoako Agyemang] · [sudoNard]*
