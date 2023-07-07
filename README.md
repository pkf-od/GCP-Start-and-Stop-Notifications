# GCP Start and Stop Notifications
- *The implementation of email notifications for when a specific Google Cloud VM instance is started or stopped*
- *Created using Logs Explorer queries and Alert Policies*

<br>

# Setting up Start/Stop Email Notifications

## Step 1: Creating the Query
1. Navigate to `Logs Explorer` in the Google Cloud Console.
2. Click on the `Show Query` slide bar to enable the query editor.
3. Enter the following query to create a log based alert: <br><br>
*For Start Notifications:* <br><br>
![Start Query](/Images/Queries/StartQuery.png) <br><br>
*For Stop Notifications:* <br><br>
![Stop Query](/Images/Queries/StopQuery.png)<br>

## Step 2: Creating the Alert Policy
1. Click `Create alert` at the bottom of the query editor.
2. Under `Alert details`, enter VM Started or VM Stopped as the name (depending upon which notification you are setting up). <br><br>
![Alert Details](/Images/AlertPolicy/AlertDetails.png)
3. The `Choose logs to include in the alert` section should auto-fill with the query that you entered previously.
4. For `Set notification frequency and autoclose duration`, set `Time between notifications` to 5 min and `Incident autoclose duration` to 1 hr. <br><br>
![Notification Frequency](/Images/AlertPolicy/NotificationFrequency.png)<br>

## Step 3: Setting up the Notification Channels
1. Click on the dropdown arrow next to `Notification Channels`, then click on `Manage Notification Channels`. <br><br>
![Notification Channels](/Images/NotificationChannels/NotificationChannels.png)
2. This will take you to the `Notification channels` section in `Monitoring`.
3. From here, scroll down to the bottom where you will find the `Email` section. <br><br>
![Email Section](/Images/NotificationChannels/EmailSection.png)
4. Click on `Add new` in the top right. In the window that appears, enter an email address and a display name for this address. Then click `Save`. <br><br>
![Create Email](/Images/NotificationChannels/CreateEmail.png)
5. Repeat step 4 for all email addresses that you want to receive Start/Stop notifications.
6. Return to the Alert Policy page. Refresh the Notification Channels, then select the channels that you just created. Click `OK`.
7. When you are finished setting up the Alert Policy, click `Save` to create the policy.

*Perform Steps 1 to 3 twice (once for Start Notifications and once for Stop Notifications).
When you are done, you should have two alert policies!*

### You have now created Alert Policies for Start/Stop Email Notifications!