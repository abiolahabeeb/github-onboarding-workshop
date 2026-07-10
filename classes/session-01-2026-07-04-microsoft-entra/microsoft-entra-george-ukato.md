# My Notes — \[George Ukato]

## Key Concepts I Learned

<!-- Write the main ideas covered in today's session -->

* **Authentication Strengths in Microsoft Entra ID;** Authentication Strengths allow organizations to define the level of authentication required to access resources. They can be categorized as follows:**\[i]** Password less(Strongest)- e.g FIDO2 Security Keys, Windows Hello for Business. **\[ii]** Multifactor Methods- e.g OATH hardware tokens, Sms/voice call(legacy). **\[iii]** Single Factor- e.g Passwords, Security Questions(SSPR Only), Email (SSPR Only). Restructure to make more sense.



* **Conditional Access Policy** in Microsoft Entra ID is a security feature that controls who can access an application, from where, and under what conditions. It allows organizations to enforce access rules based on user identity, device status, location, risk level, or the application being accessed. Conditional Access follows an "if this, then that" approach: If a user signs in from an unknown location, Then require Multi-Factor Authentication (MFA).If a user tries to access Microsoft 365 from an unmanaged device, Then block access or require the device to be compliant.





* **Privileged Identity Management**- Enables organizations to manage, control and monitor access to important organizational resources.

\---

## Lab / Hands-On Work

<!-- Describe what you did in the lab. Include steps, commands, or screenshots descriptions -->

### What I did

* I was able to configure conditional access when my tenant was still active. If a user signs in to Microsoft 365 from outside Nigeria using an unmanaged laptop, then they must complete MFA before access is granted. I assigned this policy to some users and was able to test it. 
* For PIM, I followed the Demo done by the Mentor and I am looking forward to perform hands-on lab once we are given our test tenant. 



### What happened / Result



* The conditional access configuration was successful.



### Challenges I faced.



* I was unable to do lab for PIM because I do not have an active tenant.







## My Takeaways

<!-- What was most valuable to you personally from this session? -->



* Today's session gave me a solid understanding of how to manage, control, and monitor administrative access using Microsoft Entra Privileged Identity Management (PIM), which provides Just-in-Time (JIT), time-bound, and approval-based privileged access.
* PIM requires a Microsoft Entra ID premium P2 License. Also, E5 license also gives this PIM features.





## Questions I Still Have

<!-- Anything you want to follow up on or ask the mentor -->

* Please When will our test tenant be provided?





\---





## Resources I Found Useful

<!-- Any links, docs, or Microsoft Learn modules you found helpful -->



* The class video shared by our mentor, Emmanuel Itoje, before the session was very helpful. It provided a detailed explanation of Privileged Identity Management (PIM), which made it easier to understand the concepts discussed during the class.





*Submitted by: \[George Ukato] · \[gukato]*

