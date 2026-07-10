\---

## Key Concepts I Learned

<!-- Write the main ideas covered in today's session -->

* I learnt that securing API integrations for Microsoft 365 Copilot declarative agents using two common authentication methods: API keys and OAuth 2.0.
* API key authentication provides a simple way for an application to access an API by sending a unique key with each request,to protect sensitive credentials.
* I learnt that API keys should never be stored directly in source code, instead, they should be securely managed through services such as Azure Key Vault.
* API keys are convenient to use thanks to their simplicity. To call an API secured with an API key, all you need to do is to include the API key in the API request. The API then validates the key and either handles the request or rejects it with an authentication or authorization error. This simplicity comes however at a cost. API keys don't authenticate the user which means that the API can't act on the user's behalf. All users calling the API with the same API key, have the same permissions.

\---

## Lab / Hands-On Work

<!-- Describe what you did in the lab. Include steps, commands, or screenshots descriptions -->

I haven't done any labs yet, i am still having issues with getting my debit card

### What I did



### What happened / Result



### Challenges I faced



\---

## My Takeaways

<!-- What was most valuable to you personally from this session? -->



An API key is a secret value that you should never share publicly. When you build an API plugin that integrates with an API secured with an API key, you store the API key in a secure storage location in Microsoft 365, also known as vault. 

\---

## Questions I Still Have

<!-- Anything you want to follow up on or ask the mentor -->

* I really would appreciate it if we get to talk about APIs well in class
* 

\---

## Resources I Found Useful

<!-- Any links, docs, or Microsoft Learn modules you found helpful -->

* 

\---

*Submitted by: Mathias Eleluwor · Mattech-lab*

