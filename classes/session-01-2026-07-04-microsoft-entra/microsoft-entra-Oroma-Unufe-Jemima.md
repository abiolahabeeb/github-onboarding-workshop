My Note Oroma Unufe

Cloud and AI Security Bootcamp – Class Notes
Date: Wednesday, July 8, 2026
Topic
Secure Access to Resources Using Microsoft Entra

Session Overview
Today's session focused on how Microsoft Entra helps organizations secure access to resources through strong identity and access management. The class combined theoretical explanations with practical demonstrations to show how authentication, authorization, Conditional Access, and Privileged Identity Management (PIM) work together to protect organizational resources.

Key Concepts Covered
1. Authentication
Authentication is the process of verifying a user's identity before granting access to a system.

Examples include:

• Username and password
• Multi-Factor Authentication (MFA)
• FIDO2 security keys
• Other supported authentication methods

2. Authorization
Authorization determines what an authenticated user is allowed to access or perform after successfully signing in.
Authentication = Who you are
Authorization = What you are allowed to do

3. Multi-Factor Authentication (MFA)
MFA provides an additional layer of security by requiring users to verify their identity using more than one authentication factor.

Benefits include:
• Reduces the risk of compromised accounts
• Protects sensitive organizational resources
• Strengthens identity security

4. Single-Factor Authentication
Using only a username and password is considered single-factor authentication and presents a higher security risk because stolen credentials can easily be used by attackers.

Conditional Access
Conditional Access allows organizations to enforce security policies based on predefined conditions before granting access.
During the practical session, we learned how to create a Conditional Access policy in Microsoft Entra.
The policy can evaluate conditions such as:
• Users and groups
• Applications
• Device platforms
• Locations
• Client applications
• Device filters
• Authentication flows
• Sign-in risk

Organizations can configure policies to:
• Require MFA
• Require a specific authentication strength
• Block access when conditions are not met
• Allow access only from trusted locations or compliant devices

We also learned the importance of:
• Carefully selecting target users and groups
• Excluding emergency or break-glass accounts
• Using Report-only mode to test policies before enforcing them

Session Controls
The instructor explained Session Controls, which help manage user sessions after authentication.
Examples include:
• Sign-in frequency
• Persistent browser sessions
• Controlling how long users remain signed in

Authentication Methods
Microsoft Entra supports multiple authentication methods.
We learned that administrators must enable authentication methods such as FIDO2 security keys before users can configure and use them.

Privileged Identity Management (PIM)
The practical session introduced Microsoft Entra Privileged Identity Management (PIM).
PIM helps organizations manage privileged accounts by:
• Providing Just-in-Time (JIT) access
• Reducing permanent administrative privileges
• Requiring MFA before role activation
• Requiring justification before activation
• Limiting activation duration
• Maintaining audit logs for accountability

Hands-on Lab
The practical exercise focused on onboarding an administrative role into PIM.
The lab included:
• Converting permanent administrator assignments to Eligible assignments
• Requiring MFA before role activation
• Requiring justification before activation
• Setting a two-hour activation limit
• Configuring approval for role activation
• Testing the activation process
• Reviewing audit logs

Key Takeaways
• Authentication verifies identity, while authorization determines permissions.
• MFA significantly strengthens account security.
• Conditional Access enables organizations to enforce security policies based on user and device conditions.
• Report-only mode should be used to validate policies before deployment.
• PIM helps implement the Principle of Least Privilege by providing temporary administrative access through Just-in-Time activation.
• Identity security is most effective when theoretical knowledge is reinforced through practical implementation.

Facilitators
• Mr. Oghenegare Itoje – Theory Session
• Mr. Uche Azunna – Practical Demonstration
• Mr. Amos Adewale – Moderator
• Mr. Oluwatosin Ajala – Q&A Session and Next Week's Facilitator


# Microsoft Learn Module Summary

## Authenticate Your API Plugin for Declarative Agents with Secured APIs

### Objective

This module taught me how Microsoft 365 Copilot declarative agents securely communicate with external applications using API plugins. I learned the differences between API keys and OAuth 2.0 authentication and how Microsoft secures sensitive credentials using the Teams Vault.

---

# What I Learned

## 1. Declarative Agents

A declarative agent is a customized AI assistant built for Microsoft 365 Copilot. It can answer questions and perform tasks by connecting to external systems through APIs.

---

## 2. API Plugins

An API plugin acts as a **bridge** between Microsoft 365 Copilot and an external API.

The process is:

**User → Copilot → API Plugin → API → External System → Response back to Copilot**

Without the plugin, Copilot cannot retrieve live information from external applications.

---

## 3. APIs

An API (Application Programming Interface) allows two different applications to communicate with each other.

For example, a repair management system exposes an API so that Copilot can retrieve repair records.

---

## 4. Authentication vs Authorization

One of the most important lessons I learned was the difference between authentication and authorization.

**Authentication**

* Verifies who the user is.
* Usually performed by Microsoft Entra ID.
* Answers the question:

  > **Who are you?**

**Authorization**

* Determines what the authenticated user is allowed to access.
* Uses scopes contained in an access token.
* Answers the question:

  > **What are you allowed to do?**

---

## 5. API Keys

An API key is a secret string used to identify an application.

Characteristics:

* Identifies the application rather than the individual user.
* Every user using the same API key receives the same permissions.
* Must never be exposed publicly.
* Stored securely in the Microsoft Teams Vault.

---

## 6. OAuth 2.0

OAuth 2.0 is an authorization framework.

It does not authenticate users directly.

Instead:

1. The user authenticates with Microsoft Entra ID.
2. Microsoft Entra ID authorizes the request.
3. An access token is issued.
4. The API validates the access token before returning data.

OAuth allows different users to have different permissions even while using the same application.

---

## 7. Access Tokens

An access token acts like a visitor's badge.

It contains:

* User identity information.
* User permissions (Scopes).
* Expiration time.
* The application requesting access.

The API validates the token before granting access.

---

## 8. Scopes

Scopes represent permissions.

Example:

* `repairs_read` → Permission to read repair records.
* `repairs_write` → Permission to update repair records.

If an access token only contains `repairs_read`, the user cannot modify repair records.

---

## 9. HTTP Status Codes

I learned the difference between:

**401 Unauthorized**

* No valid authentication.
* Missing, invalid, or expired access token.

**403 Forbidden**

* User is authenticated.
* User does not have sufficient permissions to perform the requested action.

---

## 10. Teams Vault

Microsoft Teams Vault securely stores:

* API Keys
* Client IDs
* Client Secrets

During runtime, the API plugin retrieves these secrets securely without exposing them in the application's source code.

---

## 11. Microsoft Entra ID

Microsoft Entra ID:

* Authenticates users.
* Issues access tokens.
* Manages identities and permissions.
* Supports OAuth 2.0 authorization.

---

## 12. Azure Functions Easy Auth

Azure Functions uses Easy Auth to validate access tokens before requests reach the application code.

If the token is invalid or expired, the request is rejected automatically with a **401 Unauthorized** response.

---

## 13. PKCE (Proof Key for Code Exchange)

PKCE adds another layer of security to the OAuth authorization flow.

It helps protect authorization codes from being intercepted by attackers.

---

# Practical Setup

To prepare for the practical exercise, I successfully completed the following setup:

* Installed **Visual Studio Code**.
* Installed **Node.js (v24.18.0)**.
* Verified **npm (v11.16.0)**.
* Installed the **Microsoft 365 Agents Toolkit** extension in Visual Studio Code.

While configuring the toolkit, I discovered that it requires a **Microsoft 365 work or school account** connected to a **Microsoft 365 tenant with Copilot enabled**. My personal Microsoft account (linked to Gmail) could not be used to sign in.

During a previous bootcamp session, the facilitators informed us that participants would be provided with a Microsoft 365 tenant. I am currently waiting for the tenant details so that I can complete the practical exercise of building and testing the Copilot API plugin.

---

# Reflection

This module greatly improved my understanding of how Microsoft 365 Copilot securely interacts with external applications. I now understand how APIs, API plugins, API keys, OAuth 2.0, Microsoft Entra ID, access tokens, scopes, Teams Vault, and Azure Functions work together to provide secure authentication and authorization. I also gained practical experience preparing a development environment with Visual Studio Code, Node.js, npm, and the Microsoft 365 Agents Toolkit in readiness for building and testing a secure Copilot API plugin.