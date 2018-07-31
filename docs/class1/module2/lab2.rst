Lab 2.2: Automating device backup and archiving a copy of the backup file
-------------------------------------------------------------------------

BIG-IQ provides the ability to backup individual or groups of managed devices on an ad-hoc or a scheduled basis. The admin can decide how long to retain the backups on BIG-IQ and has the option of archiving a copy of the UCS backup off to an external device for DR or deeper storage purposes.
In this scenario, we are going to schedule a nightly backup that archives a copy off to our archive for DR purposes.

1. Click on the **Back Up & Restore** on the left-hand menu
2. Click on Backup Schedules

.. image:: ../pictures/module2/img_module2_lab2_1.png
  :align: center
  :scale: 50%

3. Click the **Create** button in the main pane
4. Fill out the Backup Schedule

- Name: SeattleNightly
- Local Retention Policy: Delete local backup copy 3 days after creation Backup Frequency: Daily
- Start Time 00:00 Eastern Standard Time
- Under Devices, select the device radio button
- Select the **SEA-vBIGIP01.termmarc.com**
- Archive: Store Archive Copy of Backup
- Location: SCP
- IP Address: 10.1.10.80
- User name: f5
- Password: default
- Directory: /home/f5

5. Click **Save & Close** to save the scheduled backup job.
