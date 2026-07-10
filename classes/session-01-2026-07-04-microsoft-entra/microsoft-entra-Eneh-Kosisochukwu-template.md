# My Notes — [ENEH KOSISOCHUKWU]

## Key Concepts I Learned
- Learned that OAuth is a more secure, industry-standard authorization protocol that authenticates users individually using access tokens, allowing APIs to act on behalf of the signed-in user.
- Learned that at runtime, the declarative agent retrieves the stored credentials from the Vault and uses them to authenticate and call the API securely.
- Learned that enabling Proof Key for Code Exchange (PKCE) provides an additional layer of security for OAuth integrations and is recommended by Microsoft.
- Learned that during development, API keys and OAuth credentials can be registered using the Teams Developer Portal or Microsoft 365 Agents Toolkit, while production credentials are typically managed by an administrator.
---

## Lab / Hands-On Work
- I had issues retreiving the actual zip file so i couldnt follow the actual lab on the module but i researched for a lab i could do to understand the topic.

### What I did
I integrated a Microsoft 365 Copilot API plugin with an API secured using an API key while following security best practices by storing the API key in the Microsoft 365 Vault instead of exposing it in the application.

## Tools Used
Microsoft 365 Teams Developer Portal
- Microsoft 365 Copilot
- NASA Open API (Astronomy Picture of the Day API)

### What happened / Result
- first obtained a free API key from the NASA API portal
<img width="1626" height="470" alt="image" src="https://github.com/user-attachments/assets/65c6fa23-9a0b-4fc8-b102-0c9bbe7a8254" />

- Registered the NASA API key in the Microsoft 365 Vault.
<img width="831" height="370" alt="{07680086-30E0-40D6-874D-D4FF4E82AEC3}" src="https://github.com/user-attachments/assets/86ed4a76-1e44-4d5f-af0f-d00831d9c593" />

- Verified that the API key is securely stored in the Microsoft 365 Vault and is not exposed in the application.
  <img width="1818" height="264" alt="image" src="https://github.com/user-attachments/assets/d257c5e3-ce9c-4dfd-9ef7-b19122b72482" />

  
- Confirmed that the API plugin references the **API Key Registration ID** instead of the actual API key.
  <img width="1938" height="408" alt="image" src="https://github.com/user-attachments/assets/da583385-dbb8-4744-9d43-6b616a134000" />

- The Agents Toolkit provision succeeded, and the app is visible in the Developer Portal.
<img width="2536" height="402" alt="image" src="https://github.com/user-attachments/assets/041de8a3-dab4-47fe-944f-db09bd11aad0" />

- Confirmed that the API and the agent are actually working as intended
<img width="497" height="301" alt="{A6896D4C-0B01-4CBB-92A7-00E6918BB6B9}" src="https://github.com/user-attachments/assets/dc473e85-90c9-4a35-8b89-bc4d535a946a" />

- Completed the Module
  
<img width="2428" height="1304" alt="image" src="https://github.com/user-attachments/assets/3ab74b01-c7b5-4115-b6e6-d4bbe5ea391d" />


## Outcome
The NASA API key was successfully registered in the Microsoft 365 Vault. An API Key Registration ID was generated, enabling Microsoft 365 Copilot to securely retrieve the API key at runtime and authenticate requests to the protected API without exposing sensitive credentials.

### Challenges I faced
- I faced authorization issue because i was using a managed microsoft 365 account.
---

## My Takeaways

- Understood the role of the Microsoft 365 Vault in securely storing API credentials.
- Learned that API plugins reference an **API Key Registration ID** rather than the API key itself.
- Understood that Microsoft 365 Copilot retrieves the API key from the Vault during runtime before making API requests.
- Recognized that storing secrets in the Vault enhances security and allows API keys to be updated without modifying or redeploying the plugin.

---

## Questions I Still Have

<!-- Anything you want to follow up on or ask the mentor -->

-
-

---

## Resources I Found Useful

<!-- Any links, docs, or Microsoft Learn modules you found helpful -->

-

---

*Submitted by: ENEH KOSI · KoceeEneh*
