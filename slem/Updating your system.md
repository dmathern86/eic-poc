# Updating your system
Log in to the system. After your system is registered, you can update it with the transactional-update command.
```
transactional-update
```
# Disabling automatic reboot
By default SUSE Linux Enterprise Micro runs a timer for transactional-update in the background which could automatically reboot your system. Disable it with the following command:
```
systemctl --now disable transactional-update.timer
```
