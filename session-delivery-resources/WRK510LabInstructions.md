<!--TOC-->
  - [Launching Data Explorer](#launching-data-explorer)
    - [Updating Content Explorer List Viewer Permissions](#updating-content-explorer-list-viewer-permissions)
    - [Viewing which SharePoint sites have sensitive data in them](#viewing-which-sharepoint-sites-have-sensitive-data-in-them)
  - [SharePoint Site Permissions](#sharepoint-site-permissions)
  - [Running Sharing Reports in OneDrive](#running-sharing-reports-in-onedrive)
  - [Setting the default link type](#setting-the-default-link-type)
    - [Setting the Tenant Default](#setting-the-tenant-default)
    - [Setting at the Site Level](#setting-at-the-site-level)
  - [Default Link expiration](#default-link-expiration)
  - [Creating a DLP Policy](#creating-a-dlp-policy)
  - [Creating a Retention Policy](#creating-a-retention-policy)
<!--/TOC-->

## Launching Data Explorer

1. Launch Lab Environment
2. Launch Microsoft Edge via the icon on the desktop
3. Type `https://purview.microsoft.com` into Edge
4. Login using the administrator credentials provided in the lab
5. Acknowledge any prompt around the new purview admin portal
6. Click on **Solutions** on the left-hand side and then **data loss prevention**
7. Expand **Explorers** in the left nav rail and click on **Data Explorer**
8. Click on **Credit Card Number** within the list in Data Explorer
9. Click on **SharePoint** on the right-hand side. You **WILL** be prompted that you do **NOT** have permissions yet.
10. Click **Close** on the prompt

### Updating Content Explorer List Viewer Permissions

1. Click on **Settings Icon** on the left nav rail
2. Select** Roles and Scopes**, and then **Role Groups**
3. In the search bar at the top right type in “Content Explorer”
4. Select the **Content Explorer List Viewer** group and then click Edit at the top
5. Click on the **Choose Users** button on the screen
6. In the search bar at the top type in “admin”
7. Select the **MOD Administrator Account** and then click the **Select** button at the bottom and then click on **next**
8. Wait on submitting to finish and then click** Done**
9. Close the Browser window (IMPORTANT)

### Viewing which SharePoint sites have sensitive data in them

1. Launch Microsoft Edge via the icon on the desktop
2. Type `https://purview.microsoft.com` into Edge
3. Login using the administrator credentials provided in the lab
4. Acknowledge any prompt around the new purview admin portal
5. Click on **solutions** on the left-hand side and then **data loss prevention**
6. Expand **Explorers** in the left nav rail and click on **Data Explorer**
7. Click on **Credit Card Number** within the list in Data Explorer
8. Click on **SharePoint** again this time you can see the Site that’s contain Credit Card data. These are the sites you should be running reviews on.

## SharePoint Site Permissions

1. Click on the **App launcher**, click on **SharePoint icon**
2. Click on **My Sites** up at the top
3. Select a site
4. Click on the **Settings gear** icon at the top right
5. Click on **Settings**
6. Click on **Site Usage**
7. Scroll down to the “Shared with external users” and Click on **“Run report”**
8. Click on **Save** to save the report

## Running Sharing Reports in OneDrive

1. Click on the **App launcher** up at the top, then click on the **OneDrive icon**
2. Click on the **Settings** icon in the top right, then click on **OneDrive settings** at the very top of the list
3. Click on **More Settings** on the left nav rail
4. Click on **Run Sharing Report**
5. In the destination box click on **Save**

## Setting the default link type

### Setting the Tenant Default

1. Launch Edge and go to `https://admin.microsoft.com`
2. Click on the **SharePoint Admin Center** in the left nav rail
3. In the SharePoint Admin Center expand **Policies**
4. Click on **Sharing**
5. Scroll down to the File and folder links section
6. Select the **“Only people in your organization”** radio button
7. Select the **“View”** radio button under “Choose the permissions that’s selected by default for sharing links”
8. Click the **Save** button

### Setting at the Site Level

1. In the SharePoint Admin Center Expand** Sites** in the left nav rail and Select **Active Sites**
2. Click on the **3 dots** at the top and then click **Sharing**
3. Under the External sharing section select **“Only People in your organization”**
4. Expand the **Default sharing link type**
5. Clear the checkbox on **“Same as organization level setting”**
6. Select **“People with existing access”**
7. Click **Save**

## Default Link expiration

1. Launch the SharePoint Admin Center
2. Expand **Policies**, and click on **Sharing**
3. Scroll down to the **“Choose expiration and permissions options for Anyone links”**
4. Select the box next to **“These links must expire with this many days”**
5. Type in 15**** in the days box
6. Click on the drop down for Files and change it to **View** from View and Edit
7. Scroll down and Click **Save**

## Creating a DLP Policy

1. Launch Edge and go to `https://purview.microsoft.com`
2. Click on **Solutions** and then click on **Data Loss Prevention**
3. Click on **Policies**
4. Click on **“Create Policy”**
5. Click **Financial**
6. Click **U.K. Financial Data**
7. Click **Next**
8. Name the Policy
9. On the Assign Admin units page click **Next**
10. On the Locations page review what Locations are selected and then click **Next**
11. On the Define Policy Settings page, confirm the policy you have selected and then click **Next**
12. On the Info to protect page, confirm the “Detect when this content is shared from Microsoft 365” is checked and click **Next**
13. On the Protection actions page, confirm and change these settings as you see fit and then click **Next**
14. On the Customize access and override settings page, confirm and adjust these settings as you see fit and then click **Next**
15. On the Policy Mode page, select the **“Turn the policy on immediately”** radio button and click **Next**
16. On the Summary page, confirm everything you have selected and then finally click **Submit**
17. On the Finish page, review any recommendations and then click **Done**

## Creating a Retention Policy

1. Launch Edge and navigate to `http://purview.microsoft.com`
2. Click on **Solutions** and then click on **Data Lifecycle Management** on the left nav rail
3. Click on **Policies** on the left and then **Retention Policies**
4. Click **new retention policy**
5. On the Name your retention policy page, type in** “10 year deletion policy”** for the policy name and click **Next**
6. On the Policy Scope page click **Next** as we want it to apply to the full directory
7. Select the *Static* Radio button and click **Next**
8. Confirm the correct locations are selected and then click **Next**
9. In Retention Settings change “Retain items for a specific period" to **10 years**
10. Change “Start the retention period based on” to **“when items were created”**
11. Change “At the end of the retention period” to **“Delete items automatically”**
12. Click **Next**
13. Review the Finish Page and then click **Submit**
14. Review recommendations and then click **Done**