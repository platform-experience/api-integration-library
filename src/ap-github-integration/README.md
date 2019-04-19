# Github Integration

## Description

A simple GitHub integration for creating incidents from a local JSON config.

## Screenshot

![Github Integration](https://raw.githubusercontent.com/platform-experience/api-integration-library/master/src/ap-github-integration/images/ap-github-integration.png)

## Additional Information/Notes

Simply pushing the configured JSON file to the designated GitHub repository will generate an incident on your target instance; once the setup process is complete.

Note: this integration will operate only with public GitHub repositories.

## Getting Started

### Update Set Installation

1. Download and install the update set.

   **[ap-github-integration.u-update-set.xml](https://github.com/platform-experience/api-integration-library/blob/master/src/ap-github-integration/ap-github-integration.u-update-set.xml)**

   Directions on loading an update set from the SN product documentation. [Load a customization from a single XML file](https://docs.servicenow.com/bundle/madrid-application-development/page/build/system-update-sets/task/t_SaveAnUpdateSetAsAnXMLFile.html#t_LoadCustomizationsFromAnXMLFile)

### GitHub Setup

1. Setup a new repository or use an existing one

1. [Create GitHub webhook](https://developer.github.com/webhooks/creating/)

1. Webhook configuration

   Set the Payload URL for the target instance. Make sure to update the example instance name and remove the curly braces.

   `https://{example.service-now.com}/api/snc/github_inbound/event`

   The content type will be **application/json**, set **Enable SSL verification**, select **Just the push event** and make sure the webhook is active.

### JSON Config

1. Create a JSON config file for the incident in your local repository

   ```bash
   touch incident.json
   ```

   The name can be anything as long as the extension is `.json`.

1. Create a minimal or complete JSON incident configuration

   Minimal Config

   ```json
   {
     "caller": "Abraham Lincoln",
     "short-description": "Howdy from GitHub."
   }
   ```

   Complete Config

   ```json
   {
     "active": true,
     "caller": "Abraham Lincoln",
     "category": "network",
     "contact-type": "email",
     "impact": 1,
     "short-description": "AI attack on network!",
     "state": 2,
     "subcategory": "dns",
     "urgency": 1
   }
   ```

### GitHub Push

Sample git workflow to push changes and generate an incident.

1. Add the file

   ```bash
   git add .
   ```

1. Commit changes

   ```bash
   git commit -a -m "Created a new incident config"
   ```

1. Push changes to GitHub

   ```bash
   git push -u origin master
   ```
