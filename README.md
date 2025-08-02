# PnPRobocopy
PowerShell drive PnP script that mimics recursive robocopy base functionality. 

This script was designed with some help from CoPilot. 

Working with a client who migrated from Google Drive to One Drive using M365 admin migration tools. They began working in the new folder structures (A), but didn't realize soon enough there was items left behind. They copied all Google files again into a different structure (B), and now left with two disparate systems. We decided best steps to move forward would be to copy all data from the FULL migration (B), into the already worked in and redesigned (A). While possibly ending up with duplicate files/structures, this had the least likely chance of writing over new information since the migration.  

Trying to work as an admin in OneDrive client is literally the worst. After a half a day of simple hand checking and drag and drop/overwrite functionality of NTFS, we realized the next problem, deep seeded folder structure, breaking name length conventions in both desktop and cloud environments. Copy/Cut Paste would fail with either nameLen errors or sameName errors, all pointing to path length issues. 

OneDrive is natively SharePoint, so connecting to PnP services via PowerShell 7 was the next logical step, bypassing both workstation NTFS and cloud file storage UI limitiations. Once connected, it was finding a recursive, report heavy process, where we could carefully comb through structures and see data migrating in real time, with errors and file structure changes being flagged. This script is slow, but far more effective and data careful than other more slash and burn attempts. 

As of today, this was first draft MVP, just getting us through the process and getting the client back to work. 
