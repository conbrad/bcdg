# GitHub upgrade transition guide

This transition guide offers more detailed information about IDIRs and GitHub changes as they relate to the GitHub SSO upgrade. 

We published more about [the SSO upgrade](bc-government-organizations-in-github.md#single-sign-on-is-coming-to-the-bc-governments-github-organizations) on DevHub. 

## IDIRs

We use [Jira Service Manager](https://citz-do.atlassian.net/servicedesk/customer/portal/2) (JSM) for user requests that cannot be completed on GitHub. If there’s a topic isn’t covered in the guide, please fill out a form to open a ticket.

### Compatible IDIRs for the GitHub SSO upgrade

Our organization has many different types of IDIRs, such as:
- Primary IDIRs for employees
- Secondary IDIRs for testing
- Generic IDIRs linked to shared inboxes
- Contractor IDIRs

As we upgrade GitHub. we focus on 2 types of IDIRs:
- Primary IDIRs for employees
- Contractor IDIRs
 
### Primary IDIRs for employees
B.C. Government employees have the default configuration compatible with SSO. [DevHub has instructions to link your IDIR to GitHub](bc-government-organizations-in-github.md#single-sign-on-is-coming-to-the-bc-governments-github-organizations).
 
### Compatible IDIRs for contractors
If a user is a contracted worker, then the process may be more complex, depending on IDIR types. The table below offers an overview between P2 and E5, IDIRs compatible with the GitHub SSO upgrade.
We don’t foresee any technical issues with SSO if contractors have either IDIR type. If this isn’t the case, please fill out a form to open a ticket on [our Jira Service Manager](https://citz-do.atlassian.net/servicedesk/customer/portal/2).
 
P2 and E5 IDIR comparison
Column 1 lists IDIR features, column 2 has P2 features, and column 3 has E5 features.
 

|                     | P2 IDIR       | E5 IDIR       |
|---------------------|---------------|---------------|
| Cost                | $2 per month  | $57 per month |
| Office 365 license  | No            |  Yes          |
| Expiry date         | Yes           |  Yes          |


Please see [Service Bulletin 1350](https://ociomysc.service-now.com/sp?id=kb_article&sys_id=7a69f65fdbff9d10fa86193813961978&spa=1) for more information.

Contract managers must keep expiry dates updated because our team doesn’t have the ability to submit orders on behalf of ministries. 

It’s very likely contractors already with IDIRs have P2. If linking doesn't work, please call 7-7000 or open a ticket to confirm through [MyService Centre](https://ociomysc.service-now.com/sp?id=ocio_sr_incident_management).
 
### Contractors without IDIRs
Each ministry has an authorized user who submits orders in [MyService Centre](https://ociomysc.service-now.com/sp?id=ocio_sr_incident_management). Please reach out to them as soon as possible to order an IDIR.
Multiple IDIRs.

Developers with multiple IDIRs can link their most permanent IDIR to their GitHub ID. They can change IDIRs at any time. We tested and can confirm that users make changes on their own.

The important things to keep in mind are:
- The IDIR must not be expired
- Our team cannot manage IDIR expiry dates
 
If you don’t see information that could be helpful on this guide, please let us know through [our Jira Service Manager](https://citz-do.atlassian.net/servicedesk/customer/portal/2).

## Technical information 

After July 30th, 2024, users cannot access bcgov if they didn’t link IDIRs and GitHub IDs. When SSO enablement happens, there are mechanisms in the system that force an IDIR login when you use your GitHub to login.

Our technical transition guide offers more details and helps GitHub users prepare for the upgrade.

### User impacts 
 
The users impacted are: 

- Users with accounts attached to the [bcgov GitHub organization](https://github.com/bcgov). 
- Users who use GitHub as their authentication method to login to: 
    - [Private Cloud](https://developer.gov.bc.ca/docs/default/component/platform-developer-docs),  
    - [Public Cloud](https://developer.gov.bc.ca/docs/default/component/public-cloud-techdocs), 
    - [Stack Overflow](https://stackoverflow.developer.gov.bc.ca/),  
    - [Rocket.chat](https://chat.developer.gov.bc.ca/),  
    - Any other custom apps owned by the province that use membership in the bcgov organization to authenticate and authorize users 
 - Teams relying on integrations that need access to the bcgov org, for example: 
    - GitHub or OAuth apps to automate the release or testing of your code, including 3rd party security tools 
    - Access tokens and/or SSH keys that your app or team may rely on that will be disconnected when user access is removed, IDE or command line tools and/or automation scripts 

### Outside Collaborators

We’re starting with enabling SSO for direct government workers and contractors. After completing the transition for them, we’ll focus on enabling SSO for [outside collaborators](https://docs.github.com/en/organizations/managing-user-access-to-your-organizations-repositories/managing-outside-collaborators/adding-outside-collaborators-to-repositories-in-your-organization).

Moving forward, **bcgov** GitHub organization needs mandatory and full membership. An option won’t be available to add outside collaborators anymore. 

#### Distinguishing between outside collaborators and contractors 

Outside collaborators aren’t members of B.C. Government’s GitHub organizations.  If the GitHub banners reminding users to upgrade to SSO doesn’t come up for you, then you’re likely an outside collaborator. 

### IDIRs

#### IDIR expiry

Government employees don’t have expiry dates on their IDIR, only contractor IDIRs do. If you’re a contractor and your IDIR expires, then you won’t have general access anymore. Each ministry must manage contractor IDIRs because our team doesn’t have the capability to change expiry dates.

Our [transition guide about IDIRs](#idirs) has more relevant information.

#### Multiple IDIRs

Developers with multiple IDIRs can link their most permanent IDIR to their GitHub ID. They can change IDIRs at any time. We tested and can confirm that users make changes on their own.

The important things to keep in mind are:
- The IDIR must not be expired
- The Developer Experience team cannot manage IDIR expiry dates for teams

### No new GitHub ID needed

GitHub differs from other tools that use IDIR as the user account to access services.

The reason is due to GitHub’s open source code community ecosystem. A part of our commitment to open government is the bcgov GitHub organization. We set up GitHub accounts to be associated with many different repositories and organizations because throughout their careers, developers contribute to many different open projects and organizations.

With the GitHub SSO upgrade, contractors and developers working in the bcgov GitHub organization will continue to use their GitHub to login to access GitHub. The extra step is the prompt to login to IDIR to comply with security policies. 

### Resetting GitHub Keys

VS Code users get prompts automatically. If you don’t use VS Code, there are 3 GitHub guides that can help:
- [About authentication with SAML SSO](https://docs.github.com/en/enterprise-cloud@latest/authentication/authenticating-with-saml-single-sign-on/authorizing-an-ssh-key-for-use-with-saml-single-sign-on#about-authorization-of-ssh-keys)
- [Authorizing a personal access token for use with SAML single sign-on](https://docs.github.com/en/enterprise-cloud@latest/authentication/authenticating-with-saml-single-sign-on/authorizing-a-personal-access-token-for-use-with-saml-single-sign-on)
- [Authorizing an SSH key for use with SAML single sign-on](https://docs.github.com/en/enterprise-cloud@latest/authentication/authenticating-with-saml-single-sign-on/authorizing-an-ssh-key-for-use-with-saml-single-sign-on#authorizing-an-ssh-key)

### GitHub bcgov organization removal

After July 30th, 2024, if a contractor IDIR expires, they won’t automatically be removed from the bcgov GitHub organization. This may change in the future.

Although contractors won’t be removed, they won’t have write access the bcgov GitHub organization.

We continue to work towards connecting IDIR expiry to automatic account removal.
