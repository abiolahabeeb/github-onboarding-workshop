# My Notes — Okoruwa Obehi Emmanuel

Here's the completed template based on the Microsoft Learn module you provided.

# Key Concepts I Learned

* Declarative agents for Microsoft 365 Copilot can be extended with API plugins to securely access external applications and perform actions.
* API plugins can be secured using either **API Keys** or **OAuth**, with sensitive credentials stored securely in the Microsoft 365 vault instead of the application.
* Microsoft 365 Agents Toolkit simplifies creating, configuring, registering, and testing declarative agents and API plugins while keeping secrets secure.

---

# Lab / Hands-On Work

## What I did

* Created a new **Microsoft 365 Copilot Declarative Agent** project using the Microsoft 365 Agents Toolkit in Visual Studio Code.
* Added a new API plugin secured with an API Key (Bearer Token Authentication).
* Examined the OpenAPI (`repair.yml`) specification to understand API key and OAuth security configurations.
* Reviewed the TypeScript implementation that validates API keys and OAuth access tokens.
* Configured the API key by generating a new key using `npm run keygen` and storing it in the `.env.local.user` file.
* Explored how Microsoft 365 Agents Toolkit registers API keys and OAuth credentials in the Microsoft 365 vault.
* Learned how OAuth client information (Client ID, Client Secret, Authorization URL, Token URL, and scopes) is securely stored and managed.
* Examined Azure Functions authentication settings configured through Bicep and Microsoft Entra ID.
* Tested both the API Key and OAuth secured declarative agents by running **Debug in Copilot (Edge)** and interacting with the custom Copilot agent.

## What happened / Result

* Successfully created and configured declarative agent projects with API plugins.
* Verified that Microsoft 365 Copilot securely retrieved API credentials from the vault instead of exposing secrets in the application.
* Confirmed that the API plugin responded to natural language prompts after authorization.
* Learned that OAuth authentication automatically obtains an access token on behalf of the signed-in user before calling the API.

## Challenges I faced

* Understanding the different authentication mechanisms between API Keys and OAuth.
* Learning how the Microsoft 365 vault stores secrets and how the registration tasks automatically update plugin configurations.
* Understanding OAuth scopes, access tokens, and how Azure Functions validates authenticated requests.

---

# My Takeaways

The most valuable lesson was learning how Microsoft 365 Copilot securely integrates with external APIs using API Keys and OAuth without exposing sensitive credentials. I also gained practical experience using the Microsoft 365 Agents Toolkit, Azure Functions, Microsoft Entra ID, and the Teams vault to build secure AI-powered declarative agents. Understanding OAuth flows, vault registration, and secure API authentication is essential for building enterprise-grade Copilot extensions.

---

# Questions I Still Have

* How can multiple APIs with different authentication methods be integrated into a single declarative agent?
* What are the best practices for managing OAuth scopes and permissions in production environments?

---

# Resources I Found Useful

* Microsoft Learn module on integrating API plugins with Microsoft 365 Copilot
* Microsoft 365 Agents Toolkit documentation
* Microsoft Entra ID documentation
* Azure Functions Authentication and Authorization (Easy Auth) documentation
* OpenAPI Specification documentation


*Submitted by: [Your Full Name] · [Your GitHub username]*
