
- [Identify Popular Sites and Oversharing](#identify-popular-sites-and-oversharing)
  - [Review Active Sites Report](#review-active-sites-report)
  - [Run a DSPM for AI Data Assessment](#run-a-dspm-for-ai-data-assessment)
- [Update, Audit, and Monitor Sharing](#update-audit-and-monitor-sharing)
  - [Disable Everyone Except External User in People Picker](#disable-everyone-except-external-user-in-people-picker)
  - [Enable Audit and Configure AI Usage Monitoring](#enable-audit-and-configure-ai-usage-monitoring)
  - [Create a DLP policy to audit sharing links](#create-a-dlp-policy-to-audit-sharing-links)
- [Configure site and document privacy setting](#configure-site-and-document-privacy-setting)
  - [Review Purview label publishing rules](#review-purview-label-publishing-rules)
- [Configure DLP for Copilot](#configure-dlp-for-copilot)
  - [Set site privacy label](#set-site-privacy-label)
  - [Set default document library label](#set-default-document-library-label)

## Identify Popular Sites and Oversharing

### Review Active Sites Report

1. Launch Lab Environment
2. Launch Microsoft Edge via the icon on the desktop
3. Type `https://admin.microsoft.com` into Edge
4. Login using the administrator credentials provided in the lab
5. Click **show all** to expand the list of admin centers and the click **SharePoint**
6. In the left-hand nav, expand **Sites** and click **Active sites**
7. Scroll to the right on the Active sites list and sort by **Page Views**

### Run a DSPM for AI Data Assessment

1. Launch Microsoft Edge via the icon on the desktop
2. Type `https://purview.microsoft.com` into Edge
3. Login using the administrator credentials provided in the lab
4. Expand **solutions** on the left hand rail and select **DSPM for AI**
5. Select **Data assessments** from the left hand pane
6. Click on **Create assessment**
7. Name the assessment **AI Tour 510** and click next
8. Select **ALL / Include All Users** and click next
9. Observe that you can choose to limit to certain sites (such as Copilot referenced) by picking **scope sites**.  Select **include all sites** and click next
10. Click **Save and Run**
11. Click **Done**
12. *Optional* Review the existing oversharing assessments to see the results of the weekly scans

## Update, Audit, and Monitor Sharing

### Disable Everyone Except External User in People Picker

1. Launch Microsoft Edge via the icon on the desktop
2. Open the link `https://learn.microsoft.com/en-us/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps#example-2`
3. Review the SharePoint Online cmdlet to disable the EEEU option

### Enable Audit and Configure AI Usage Monitoring

1. If you are not already at the Purview portal, type `https://purview.microsoft.com` into Edge
2. Expand **solutions** on the left hand rail and select **DSPM for AI**
3. Confirm that **Microsoft Purview Audit** is enabled by looking for the green checkmark in **Get started**
4. In the list of **Recommendations**, find the card titled **Control unethical behavior in AI**.  Click **View details**
5. Review the Communication Compliance policy to be created, click **Create policies**
6. Review the results and then click **Close**

### Create a DLP policy to audit sharing links

1. If you are not already at the Purview portal, type `https://purview.microsoft.com` into Edge
2. Expand **solutions** on the left hand rail and select **Data Loss Prevention**
3. In the left hand nav, click on **Policies**
4. Click **Create Policy**
5. In categories select **Financial**
6. In Regulations select **U.S. Financial Data** and then click **Next**
7. Name the policy **AI Tour 510**
8. On the Admin Units page, click **Next**
9. On the Choose where to apply the policy page, *deselect* all items except for **SharePoint sites** and **OneDrive Accounts**
10. On define policy settings click **Next**
11. Observe that the rule will detect when content is shared outside the organization. Click **Next**
12. Observe the default protection settings.  Click **Next**
13. Observe the available access and override settings. Click **Next**
14. On the Policy Mode page, chose to **Run the policy in simulation mode**.  Click **Next**
15. Click **Submit**

## Configure site and document privacy setting

### Review Purview label publishing rules

1. If you are not already at the Purview portal, type `https://purview.microsoft.com` into Edge
2. Expand **solutions** on the left hand rail and select **Information Protection**
3. In the left hand nav, select **Sensitivity Labels**
4. Expand **Confidential** and select **All Employees**
5. Click the icon titled **Edit Label**
6. On Provide basic details for this label, click **Next**
7. On Define the scope for this label, review the configured settings and see how it is set to control **Groups & Sites**.  Click **Next**
8. Review all of the configuration settings under items. Click **Next** to move through the configuration pages.
9. On Define protection settings for groups and sites, observe the settings that are configured.  Note how they align to the settings you can configure on SharePoint Sites and Teams.  Click **Next**
10. Observe that the site privacy is set to **Private**.  Click **Next**
11. Observe that the default sharing is set to **Only people in your organization**. Note how this aligns to the sharing slider in SharePoint site settings.  Click **Next**
12. Click **Cancel** to back out of the configuration pages.

## Configure DLP for Copilot

1. If you are not already at the Purview portal, type `https://purview.microsoft.com` into Edge
2. Expand **solutions** on the left hand rail and select **Data Loss Prevention**
3. In the left hand nav, click on **Policies**
4. Click **Create Policy**
5. Under Categories, select **Custom**
6. Under Regulations, select **Custom Policy**. Click **Next**
7. Name the policy **AI Tour - Block Copilot**
8. On the Admin Units page, click **Next**
9. On the Choose where to apply the policy page, *deselect* all items except for **Microsoft 365 Copilot (preview)**. Click **Next**
10. On Define policy settings, click **Next**
11. Click **Create Rule**
12. Name the rule **Copilot Sensitivity Label**
13. Click **Add condition** and select **Content Contains**
14. Click **Add** and select **Sensitivity Label**. Select the **Highly Confidential / All Employees** sensitivity label.  Click **Add**
15. Click **Add an Action** and select **Prevent Copilot from processing content (preview)**
16. Click **Save** and then click **Next**
17. Observe that you cannot run this policy in simulation mode. Click **Next** and click **Submit**

### Set site privacy label

1. Type `https://admin.microsoft.com` into Edge
2. Login using the administrator credentials provided in the lab
3. Click **show all** to expand the list of admin centers and the click **SharePoint**
4. In the left-hand nav, expand **Sites** and click **Active sites**
5. Select a **Team Site** such as the **Mark 8 Project Team**
6. Click on the **URL** to open up the site
7. Click on the **Site Gear** and select **Site Information**
8. Observe how you can set the stie privacy either by changing the privacy setting or by setting the sensitivity to Highly Confidential / All Employees. Note how the privacy settings are no longer able to be changed once the sensitivity label is selected.
9. Click **Cancel**

### Set default document library label

1. On the **Mark 8 Project Team** Click on **Documents** in the left hand Nav
2. Click on the site gear and select **Library Settings**
3. Review the list of available **Default Sensitivity Labels** and select **Confidential / All Employees**.  Click **Save**
4. Create a new **Word Document** and note how the document is immediately labeled as **Confidential / All Employees**.