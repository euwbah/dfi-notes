# 12. Android Forensics

### Dalvik Virtual Machine

Executables are `.dex` files --> "Dalvik Executables"
Application data stored in SQLite databases

### Android Security Features

- Linux kernel <--> OS security
- Mandatory application sandbox
- Secure interprocess communication
- Application Signing
- Application & User granted permissions
- Personal information is limited by permissions API

#### Rooting
- Allows users to install new OS
- Unlocks `su` powers

### Acquisition

1. Device must be configured first:
- Developer options --->
    + Allow app install from unknown sources
    + Enable USB Debugging
2. Paraben Device Seizure then will copy the `AndroidService.apk` installer to `/data/local/tmp` on the Android device.
3. This installer installs the `com.paraben.service` service as an application
4. This service enables Paraben Device Seizure to perform the acquisition
5. Once the acquisition is complete, the service will be uninstalled automatically and the `AndroidService.apk` package installer will be removed.

#### Acquisition types

**Android (logical)** plug-in:
- Select the one and only connection type
- Data type selections include:
    + Browser history
    + Calendar
    + Call History
    + Contacts
    + File System
    + Media Store
    + MMS History
    + Settings
    + SMS History
- (some) Logical folders:
    + `dalvik-cache/`: cache of `.dex` files that were run
    + `anr/`: debug/thread info with timestamps
    + `app/`: `.apk` files
    + `data/`: home of application & user data
    + `misc/`: dchp, wifi, etc. files
    + `system/`: `packages.xml` --- installed applications
    + `checkin.db`: connection info

**Android (physical)** plug-in:
- Select the one and only connection type
- Data type selections include:
    + Full Flash (physically internal storage drive)
    + Memory Card
- Gets basically everything on the phone