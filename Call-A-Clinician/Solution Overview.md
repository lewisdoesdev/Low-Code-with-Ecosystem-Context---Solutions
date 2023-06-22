# Call a Clinician
## Solution Overview
Call a Clinician is a healthcare industry solution which allows clinicians to call on the support of other clinicians with specific skillsets without having to waste time executing manual and lengthy tasks. This solution assesses whether a clinician has the skill being looked for or not and returns information on their availability as 'context' which is driven by the use of the Microsoft Graph API. 

This is a Low Code solution built on Microsoft's Power Platform and is dependent on organisations having adopted Microsoft Cloud and Microsoft 365 as their cloud and productivity suite. This solution requires premium Power Apps licenses to be available to consume the applications within the solution. 

## Skill Management App 
This solution contains two applications, with the configuration being done within the Skill Management app. This application allows admins to create skills within the system for clinicians to be matched against. Once a skill has been created, clinicians can be associated with it.

![](https://github.com/lowcodelewis/Low-Code-with-Ecosystem-Context---Solutions/blob/main/Call-A-Clinician/Skill.png)

Admins are also able to create hospital locations in the skill manegement app which are utilised in the Call a Clinician app for clinicians to set their current location. This then affects the message sent to another clinician the signed in Clinician is requesting support from, to notify them of the location they need to attend.

![](https://github.com/lowcodelewis/Low-Code-with-Ecosystem-Context---Solutions/blob/main/Call-A-Clinician/Hospital%20Locations.png)

## Call a Clinician app
In the Call a Clinician application, clinicians are able to use the app to select a skill which they need support with. The app will then find clinicians with that skill and surface each of their availability next to their names and email addresses, as well as their profile image from Microsoft 365. The clinician needing support is then able to select the Microsoft Teams icon in order to send an automated message to the other clinician, requesting that they come and support. This will let the clinician know the skill they are required for, as well as the location in the care builiding they need to come to.

To start with, the Clinician who need support will select their current location, to enable the sending of a notification to a clinician they would like support from.

![](https://github.com/lowcodelewis/Low-Code-with-Ecosystem-Context---Solutions/blob/main/Call-A-Clinician/Ward.png)

Following this, the clinician who needs support will be able to select the skill that they need support with, or that they need another clinician for.

![](https://github.com/lowcodelewis/Low-Code-with-Ecosystem-Context---Solutions/blob/main/Call-A-Clinician/Select%20a%20skill.png)

From here, the app will suggest a list of clinicians and the current clinician needing support can identify someone in the list who is marked as available and select the Teams icon to send them a message requesting their support.

![](https://github.com/lowcodelewis/Low-Code-with-Ecosystem-Context---Solutions/blob/main/Call-A-Clinician/Clinicians%20screen.png)

Once the Teams icon has been selected the clinician who has been requested to support will receive a message in Microsoft Teams.

![](https://github.com/lowcodelewis/Low-Code-with-Ecosystem-Context---Solutions/blob/main/Call-A-Clinician/Clinician%20needed.png)


