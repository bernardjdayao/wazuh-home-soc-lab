# ESCALATED ACCOUNT

## Objective
The goal of this exercise is to monitor users that have unusual privileges and permissions.

## Detection
This is part 2 of the 03-new-local-user.md exercise but this focuses more on another aspect in account/user management.

Again, create the user and verify its existence both in Wazuh Dashboard and in the Windows Environment

Once the account is created, use this Powershell command to escalate an account and change the group to where it belongs from Guest to Administrator:

Change user group to Administrator:
net localgroup Administrators soc-test /add

Then make sure to investigate it in the Event Viewer as well as the Wazuh Dashboard. 

Try deleting it and once more, investigate the Event Viewer and Wazuh Dashboard.
net localgroup Administrators soc-test /delete

Then delete the account:
net user soc-test /delete

## Result
The remarks from ID, Level and Description are the same when creating the User as seen from the evidence. The differnce is that there is a new log saying that there were changes made pertaining to the Administrators Group. Take note that I moved the freshly created account to the Administrators Group and removed it to see how Wazuh would react and it used a Level of 12 which directly labels as something that I need to look at as it is a Medium Alert

- Rule ID: 60154
- Description: Administrators Group Changed
- Level: 12

## Evidence
![alt text](<Screenshot 2026-08-11 174557.png>)

## Lesson Learned
The lesson I learned from this exercise is that a newly created account may not pose an immediate threat because it is a usual thing to have an account be made especially if it is the season for it. What is unusual for this is for an account to be created and be escalated to being an administrator which typically has the rights to view and modify critical data. Looking at this exercise this way, I am able to determine whether an attack is happening or it was approved by management, of course, depending on how granularized and modularized the roles are in an organization, then through this pattern I can know if its an attack or not, granted that there are multiple factors that I need to consider.