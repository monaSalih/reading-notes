## What is OAuth

* What is OAuth?
✔ open-standard authorization protocol or framework that describes how unrelated servers and services can safely allow authenticated access to their assets without actually sharing the initial, related, single logon credential. In authentication parlance, this is known as secure, third-party, user-agent, delegated authorization 

* Give an example of what using OAuth would look like?
✔ The simplest example of OAuth is when you go to log onto a website and it offers one or more opportunities to log on using another website’s/service’s logon. You then click on the button linked to the other website, the other website authenticates you, and the website you were originally connecting to logs you on itself afterward using permission gained from the second website.

* How does OAuth work? What are the steps that it takes to authenticate the user?
1. The first website connects to the second website on behalf of the user, using OAuth, providing the user’s verified identity.

2. The second site generates a one-time token and a one-time secret unique to the transaction and parties involved.

3. The first site gives this token and secret to the initiating user’s client software.

4. The client’s software presents the request token and secret to their authorization provider (which may or may not be the second site).

5. If not already authenticated to the authorization provider, the client may be asked to authenticate. After authentication, the client is asked to approve the authorization transaction to the second website.

6. The user approves (or their software silently approves) a particular transaction type at the first website.

7. The user is given an approved access token (notice it’s no longer a request token).
8. The user gives the approved access token to the first website.

9. The first website gives the access token to the second website as proof of authentication on behalf of the user.

10. The second website lets the first website access their site on behalf of the user.

11. The user sees a successfully completed transaction occurring.

12. OAuth is not the first authentication/authorization system to work this way on behalf of the end-user. In fact, many authentication systems, notably Kerberos, work similarly. What is special about OAuth is its ability to work across the web and its wide adoption. It succeeded with adoption rates where previous attempts failed (for various reasons).

What is OpenID?
✔ is an open standard and decentralized authentication protocol. Promoted by the non-profit OpenID Foundation, it allows users to be authenticated by cooperating sites (known as relying parties, or RP) using a third-party service, eliminating the need for webmasters to provide their own ad hoc login systems, and allowing users to log into multiple unrelated websites without having to have a separate identity and password for eac 

## Authorization and Authentication flows

* What is the difference between authorization and authentication?
✔  Authentication confirms that users are who they say they are. Authorization gives those users permission to access a resource.

* What is Authorization Code Flow?
✔ Because regular web apps are server-side apps where the source code is not publicly exposed, they can use the Authorization Code Flow, which exchanges an Authorization Code for a token.

* What is Authorization Code Flow with Proof Key for Code Exchange (PKCE)?
✔ During authentication, mobile and native applications can use the Authorization Code Flow, but they require additional security. Additionally, single-page apps have special challenges. To mitigate these, OAuth 2.0 provides a version of the Authorization Code Flow which makes use of a Proof Key for Code Exchange (PKCE).

* What is Implicit Flow with Form Post?
✔ As an alternative to the Authorization Code Flow, OAuth 2.0 provides the Implicit Flow, which is intended for Public Clients, or applications which are unable to securely store Client Secrets. 

* What is Client Credentials Flow?
✔ With machine-to-machine (M2M) applications, such as CLIs, daemons, or services running on your back-end, the system authenticates and authorizes the app rather than a user 

* What is Device Authorization Flow?
✔ With input-constrained devices that connect to the internet, rather than authenticate the user directly, the device asks the user to go to a link on their computer or smartphone and authorize the device. This avoids a poor user experience for devices that do not have an easy way to enter text. To do this, device apps use the Device Authorization Flow (drafted in OAuth 2.0). 

* What is Resource Owner Password Flow?
✔ Though we do not recommend it, highly-trusted applications can use the Resource Owner Password Flow, which requests that users provide credentials (username and password), typically using an interactive form. 