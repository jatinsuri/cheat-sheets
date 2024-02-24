# Open RBG Tips and Tricks

## Apply OpenRGB profile after resume from sleep
https://www.reddit.com/r/OpenRGB/comments/13lohol/apply_openrgb_profile_automatically_after/


- First put your PC to sleep, then wake it up.

- Open Event Viewer and browse to Windows Logs > System. There should be a recent event that coincides with waking the PC from sleep, with Source: "Power-Troubleshooter" and Event ID: 1.

- Right click this event and click "Attach Task To This Event...".

- Name it whatever you want. I went with "Restart_OpenRGB_from_Sleep".

- Set the Action to "Start a Program", and point the Program/script to your OpenRGB.exe's location.

- Add argument: --profile "INSERT PROFILE NAME HERE"

You're done! The new event will show up in Task Scheduler under Task Scheduler Library > Event Viewer Tasks. It should now run automatically whenever the system resumes from Sleep, even if it didn't work with "On workstation unlock..." selected as Trigger before.

