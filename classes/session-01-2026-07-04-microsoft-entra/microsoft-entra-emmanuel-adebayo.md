# My Notes — Emmanuel Adebayo

---

## Key Concepts I Learned

<!-- Write the main ideas covered in today's session -->
- Secure Authentication: Every access attempt by an identity requires explicit verification, which heavily relies on Multi-Factor Authentication (MFA) and Self-Service Password Reset (SSPR).
- Conditional Access: Learned how resource access can be dynamically enforced and how flexibly you can configure policies to manage user sessions based on context.
- Just-In-Time (JIT) Privileged Access: Understood that granting permanent admin roles is a security risk, and it is best practice to use Privileged Identity Management (PIM) to monitor and govern admin rights.
- Identity-Aware AI Apps: Introduced to concepts of securing modern AI applications using robust identity and access boundaries.
---

## Lab / Hands-On Work

<!-- Describe what you did in the lab. Include steps, commands, or screenshots descriptions -->
### What I did
1. Navigated through the Microsoft Entra ID portal to explore the implementation of identity security controls.
2. Explored different configuration models for Conditional Access policies, including Named Locations and custom access parameters.
3. Reviewed how to set up policies to restrict risky users or proactively prevent risky sign-ins based on threat signals.
4. Explored the Privileged Identity Management (PIM) dashboard to understand the process of granting and monitoring Entra admin roles.

### What happened / Result
- Gained a clear, practical understanding of where security policies live inside the Entra portal.
- Saw firsthand how conditional boundaries can block or allow traffic depending on user risk levels.
- Visualized the lifecycle of an eligible admin role activation within the PIM interface.

### Challenges I faced
- Keeping track of the massive amount of settings within the Entra portal can be overwhelming, but walking through the specific policy tabs helped map out the console layout.

---

## My Takeaways

<!-- What was most valuable to you personally from this session? -->
The biggest takeaway for me is learning how incredibly flexible Conditional Access is. Seeing how it can be fine-tuned to stop risky sign-ins in real-time showed me how modern companies stop cyber attacks before they even happen.

---

## Questions I Still Have

<!-- Anything you want to follow up on or ask the mentor -->
- How do we balance strict Conditional Access policies without causing too much friction for regular, non-technical users?
- Can PIM be integrated with external ticketing tools (like ServiceNow) to require an approved ticket before an admin role is activated?

---

## Task Summary
From the modules, I was able to see how microsoft 365 copilot declarative agents can connect to secured APIs using either api key or oauth authentication. With API Key authentication, a shared secret key is stored securely in a Microsoft 365 vault and used to access the API, making it simple to implement but unable to identify individual users. With OAuth, users sign in and receive access tokens that allow the API to recognize the user and enforce user-specific permissions. While API keys are best for simple application-level access, OAuth provides stronger security, delegated access, and user-level authorization, making it the preferred choice when the API needs to act on behalf of a user.

### Challenges I faced
I was not able to follow though with the module exercises as I do not have the resources to do that and I also do not have a good understanding of application development.


## Resources I Found Useful

<!-- Any links, docs, or Microsoft Learn modules you found helpful -->

-

---

*Submitted by: Emmanuel Adebayo · 19Emade*
