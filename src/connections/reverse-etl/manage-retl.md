---
title: Manage Reverse ETL Syncs
beta: false
---

View your sync history, reset your syncs, or subscribe to alerts.

## Sync overview
The Reverse ETL sync overview tab, located under **Connections > Destinations**, gives you an overview of your latest Reverse ETL syncs. 

![A screenshot of the sync overview page, which includes one failed sync and three successful syncs.](images/sync-overview.png)

You can view the following information about each sync: 
- **Latest sync**: The status of your latest sync. Syncs can either be **In progress**, **Successful**, or **Failed**.
- **Mapping**: The named mapping. 
- **Model**: The model that extracts data from your warehouse.
- **Action**: The action that your destination uses to map information from your warehouse to your downstream destination. 
- **Mapping status**: The status of your mapping - either **Enabled** or **Disabled**. 

## Sync history
Check the status of your data extractions and see details of your syncs. Click into failed records to view additional details on the error, sample payloads to help you debug the issue, and recommended actions.

To check the status of your extractions:
1. Navigate to **Connections > Destinations** and select the **Reverse ETL** tab.
2. Select the destination you want to view.
3. Select the mapping you want to view.  
4. Click the sync you want to view to get details of the sync. You can view:
    * The status of the sync.
    * Details of how long it took for the sync to complete.
    * How many total records were extracted, as well as a breakdown of the number of records added, updated, and deleted.
    * The load results - how many successful records were synced as well as how many records were updated, deleted, or are new.
5. If your sync failed, click the failed reason to get more details on the error and view sample payloads to help troubleshoot the issue.

<!--- info "Segment automatically retries events that were extracted but failed to load"
> Segment retries events for 14 days following a total or partial sync failure. Before loading the failed records on a subsequent sync, Segment checks for the latest changes in your data to ensure the data loaded into your warehouse isn't stale. If the error causing the load failure is coming from an upstream tool, you can fix the error in the upstream tool to ensure the record loads on the next sync. --->

## Reset syncs
Reverse ETL uses the Unique Identifier column to detect data changes, like new, updated, and deleted records. If you encounter an error, you can reset Segment’s tracking of this column and force Segment to manually add all records from your dataset. 

To reset a sync:
1. Select the three dots next to **Sync now**.
2. Select **Reset sync**. 
3. Click **I understand what happens when I reset a sync state**. 
4. Click **Reset sync**.

## Replays
You can choose to replay syncs. To replay a specific sync, contact [friends@segment.com](mailto:friends@segment.com). Keep in mind that triggering a replay resyncs all records for a given sync.

## Alerting
You can opt in to receive email, Slack, and in-app alerts about Reverse ETL sync failures and partial successes. 

To subscribe to alerts: 
1. Navigate to **Settings > User Preferences**. 
2. Select **Reverse ETL** in the **Activity Notifications** section.
3. Click the Reverse ETL sync status that you'd like to receive notifications for. You can select one or more of the following sync statuses:
    - **Reverse ETL sync failed**: Receive a notification when your Reverse ETL sync fails.
    - **Reverse ETL sync partial success**: Receive a notification when your Reverse ETL sync is partially successful.
4. Select one or more of the following alert options: 
    - **Enable email notifications**: Enter an email address or alias that should receive alerts.
    - **Enable Slack notifications**: Enter a webhook URL and Slack channel name.
    - **Enable in-app notifications**: Select this option to see an in-app notification.
5. Click **Create alert**.

> success ""
> If you opted to receive notifications by email, you can click **View active email addresses** to see the email addresses that are currently signed up to receive notifications. 
