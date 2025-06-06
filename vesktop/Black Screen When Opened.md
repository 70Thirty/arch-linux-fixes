Issue: Vesktop opens a blank black window instead of Discord UI

Description:
The Vesktop application appears to start normally and shows no critical errors in logs, but instead of loading the Discord UI, it opens a blank black window.

Cause:
Corrupted or problematic configuration files in ~/.config/vesktop can cause this issue.

Solution:
Delete or back up the ~/.config/vesktop directory and then restart Vesktop. This will reset the configuration and allow the UI to load normally.

Note:
Backing up is recommended if you want to preserve themes, plugins, or other custom settings.
