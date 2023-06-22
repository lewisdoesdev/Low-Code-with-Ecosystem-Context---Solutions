# Call a Clinician - Deployment Guide
This documentation describes how to install and configure the Call a Clinician solution. Configuration here includes creating an app registration in Azure Active Directory, creating an Azure Key Vault, and installing and configuring the Power Platform solution. This documentation does not cover data configuration such as creating hospital locations or matching clinicians with skills. These operations can be executed using the Skill Management app within the Call a Clinician solution once installed.

### Solution File
Start by downloading the managed solution from this repository. Save this in a safe place for when we'll need it for import later.

[Call a Clinician - Managed Solution - 1.0.0.3](https://github.com/lowcodelewis/Low-Code-with-Ecosystem-Context---Solutions/blob/main/Call-A-Clinician/CallaClinician_1_0_0_3_managed.zip)


### Create the app registration
This solution utilises Microsoft Graph within a custom connector for getting presence information about users. We will need to handle authentication for working with Microsoft Graph which we will do with an app registration and Graph delegated permissions against it.

Follow the steps below adding the Presence.Read.All delegated permission for Microsoft Graph.
- Create an app registration in Azure Active Directory
- Add the Microsoft Graph delegated permission under API permissions for Presence.Read.All
- Add the following Web platform Redirect URI – https://global.consent.azure-apim.net/redirect
- Create a client secret and note down its value
- Note down values for the app registration client id and the tenant id.

You should now have three values.
- App registration client id
- Tenant id
- Client secret value

[Find more information on Low Code Lewis to help you with creating app registrations here](https://lowcodelewis.com/blog/registering-an-app-in-azure-ad-for-use-in-power-platform-solutions)

### Create the Azure Key Vault
Now you’ll need to create a key vault to store your secret in that the custom connector in the Call a Clinician solution can reference.

To do this follow these overview steps:

- Create or use an existing resource group in Azure
- Ensure that the subscription the resource group is held in has the Microsoft.PowerPlatform provider registered
- Create a key vault in that resource group which utilises RBAC as the access configuration
- Add the Key Vault Secrets User role to both the user who will install the solution and create the reference to the key vault, and the Dataverse service principal  (00000007-0000-0000-c000-000000000000).
- Create the secret you copied earlier from the app registration in the Key Vault.

Collect the following values from your setup:

- Subscription ID
- Resource Group name
- Key Vault name
- Secret name

[For more detils on how to create the key vault, check out this blog post on Low Code Lewis, where I explained how to create the custom connector used in this solution](https://lowcodelewis.com/blog/call-a-clinician-part-2-building-the-custom-connector)

### Import the solution
The final thing to do, is import the solution! Go to make.powerapps.com and select the environment you want to put the solution in. Then select the solutions area and select import solution. Then browse and select the solution file you installed from my GitHub repository earlier and continue.

You’ll need to create connections for connectors that request this.

Once you get to the environment variables page. Paste in the values for your Client ID and Tenant ID that you noted down when you created your app registration.

Now paste in the values you noted down from creating your Key Vault in the following syntax.

```
  /subscriptions/{Subscription ID}/resourceGroups/{Resource Group Name}/providers/Microsoft.KeyVault/vaults/{Key Vault Name}/secrets/{Secret Name}
```

Finally, click import.

## More information, guidance, and build it yourself
For more information, and guidance on deploying this solution including this deployment guide with screenshots and images, check out this content on [Low Code Lewis](https://lowcodelewis.com/blog/call-a-clinician-install-and-configure-the-solution-sample).

You can also build this solution yourself by following these posts.
[Building with context - Call a clinician Part 1](https://lowcodelewis.com/blog/building-with-context-call-a-clinician-part-1)
[Call a Clinician - Part 2 - Building the custom connector](https://lowcodelewis.com/blog/call-a-clinician-part-2-building-the-custom-connector)
[Call a Clinician - Part 3 - Surfacing presence information](https://lowcodelewis.com/blog/call-a-clinician-part-3-surfacing-presence-information)
[Call a Clinician - Part 4 - Automating the contact message](https://lowcodelewis.com/blog/call-a-clinician-part-3-surfacing-presence-information)
