# Windows Under the Hood



## What is the Registry
- Registry - a binary file that can only be read by the registry editor (regedit)
- The registry contains all the settings and configurations
- `C:\Windows\System32\config`
- Registry is critical, Windows won't boot if something happens to it
- Most of the time when we need to change settings we don't use the registry editor; we use other specialized software that changes the registry for us, like the settings app, control panel, etc.
- Registry is organized into 5 root keys
    - HKEY_CLASSES_ROOT - everything in the PC is organized by what it can do
    - HKEY_LOCAL_MACHINE - defines all the settings for the computer
    - HKEY_CURRENT_CONFIG - a subset of HKEY_LOCAL_MACHINE that defines what aspects of the system are being used right now
        - BEcause different users have different settings
    - HKEY_USERS - has the different settings for each user
    - HKEY_CURRENT_USER - a subset of HKEY_USERS that defines what's being used right now
- To backup a key before editing it, right click > export

## Processes
- Two types of programs
    - Applications
    - Services
- Appications + Services = Processes
- Details tab in Task Manager shows processes
- Process explorer is a third party program alternative to task manager
