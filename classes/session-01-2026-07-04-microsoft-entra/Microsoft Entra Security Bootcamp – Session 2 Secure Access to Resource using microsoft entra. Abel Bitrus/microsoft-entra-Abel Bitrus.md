# My Notes — Abel Bitrus

## Key Concepts I Learned ##

- Managing entra ID objects using authentication methods like passowrds, MFA, passwordless authentication etc.
- Conditonal access policies which functions like a firewall, where users are authenticated and given access due to parameters like locations, operating systems etc.
- privileged identity management which is special tool for providing access to certain users who neeed special privileges to carry out administrative tasks or pertake in special projects over a limited period of time. it is used to limit users from having global access which can be compromised.

## Lab / Hands-On Work

## IMPLEMETNING CONDITIONAL ACCESS POLICY ON ENTRA ADMIN CENTER. ##

- To implement CAP on entra tenant object like groups and users. I accessed the entra admin center to find the tools needed for this lab.




- I created a user account with a display name test-user1 to carry out my lab.




- I created a group to serve as a container for my users to ensure easy management of CAP and group objects (users).




- I navigated to the conditional access tool to implement the CAP.but first I created trusted location and IP-address to ensure secure login locations for users.under the “Named Locations” option.




- I created a policy to ensure users or groups follow certain criteria or parameters to access the organizational resources.parameters include users and groups, target resources, network, conditions, access controls etc.




- I tested the user account login before activating CAP.it prompted user changed their password before proceeding to the microsft 365 environment.




- After activating CAP,the login requirements for users to use MFA was triggered.before user is prompted to change their password and continue to the Microsoft 365 environment.




- User was able to login successfully to the Microsoft 365 environment.



The above documentation show that the implementation of CAP was successful, and all CAP parameters will work as implemented based on the compliance needs configured for the organization.










## IMPLEMENTING PRIVILEGED IDENTITY MANAGEMENT ON ENTRA ADMIN CENTER ##

- To implement PIM I navigate to the ID Governance option in the entra admin panel.




- Next I went to Microsoft entra roles. Under roles I selected “windows 365 Administrator” role to setup and configure the parameters needed to activate either the eligible assignment to provide just in time access or active assignment to provide immediate or standing access.




- Configured the activate assignment parameter for PIM.



- I configured the PIM notification for the respective parties to get notified when PIM is requested or activated.




- I assigned the PIM role I activated to a user for now I am assigning the eligible assignment.






- PIM successful issued to a user.





- PIM notification to email verified.




- The user was given PIM access, now I used the entra.microsft.com link to login the user, to test PIM.I configured MFA as required by PIM roles setup. And navigated to the PIM on the entra admin center to view the role assign to the PIM user. 




- PIM activated.




PIM was successfully, roles were configured and assignment was issued to the user either eligible or active.









### AUTHENTICATE YOUR API PLUGIN FOR DECLARATIVE AGENTS WITH SECURED API’s ###

Declarative agents for Microsoft 365 copilot lets AI engineers built AI-powered assistants to function in different instances and businesses. Having this agent has become a game changer for businesses because by using the API plugins and secured API connections using API keys & Oauth,this creates a matched synergy between business operations and easy access to information that can improve business intelligence which results to business scalability and growth.

N.B

I NEED TO GO THROUGH THE EXERCISE TO FINALISE ON THIS TOPIC. BUT THE SUMMARY ABOVE GIVES A CLEAR INDICATION OF HOW AI AGENTS UTILIZE SECURED API PLUGINS FOR AI AGENTS INTEGRATION TO BUSINESS INFRASTRUCTURES.





### What I did ###

- Successfully implemented CAP.
- Successfully implemented PIM.


### What happened / Result ###

- every lab was successfully executed successfully. CAP & PIM worked fine.


### Challenges I faced ###

- I could not carry out the lab without subscribing to entra id p2 license.
- I mistakenly used login.microsoftcom to try and test PIM user login instead of entra.microsoft.com

## My Takeaways ##

I learned how to manage entra ID objects and implement the appropriate authentication and policy methods necessary for securing users access and ensuring they follow certain procedures to access organizational resources. This session ensures a security expert design a well managed entra id tenant instances and ensures the streamlining of security authentication and access parameters to ensure optimal security functions. 


## Questions I Still Have ##

- none for now.




* Submitted by: Abel Bitrus. Github: abelbitruslearnlabs