# 11. iOS Mobile Forensics & Data Types

### Partitions

- MBR
- Apple_Free
- OS Partition (HFSX)
- Apple_Free
- Data Partition

iOS built on Darwin (Unix)

### OS layers:

#### Core OS:
- File system interface
- Low-level data types
- Bonjour services
- network sockets

#### Core Services:
- Core Foundation
- CFNetwork
- SQLite
- POSIX threads, UNIX sockets interfacing

#### Media Layer:
- OpenAL
- Audio Mixing & Recording
- Video playback
- Image file formats
- etc

#### Cocoa Touch:
- touch events 
- controls 
- sensors
- localization
- camera

### Directory Structure
**Applications**: User-specific applications
**Library**: Hidden application data files
**Desktop**
**Documents**
**Downloads**
**Movies**
**Music**
**Pictures**
**Public**
**Sites**

### Forensics

Evidence found in:
- EXIF Data
- Plist Files
- Desktop Backups
- Device Data/Backup

Handling Procedure:
- Use Faraday Protection (against EMPs)
- Charge Device 100%
- Plan for long acquisition time
- Look for iTunes backups on computer

#### Acquisition Method

Using Paraben Device Seizure:
- Go to the Acquisition Wizard:
    + If not a jailbroken phone:
        * Choose the **iPhone/iPad/iTouch Advanced (Logical)** plug-in
            - Used with most iOS Devices
            - Uses iTunes to create a backup of the device
                + Backup contains user-oriented files
            - Uses the iTunes backup to perform a logical acquisition
                + Address Book
                + SMS History
                + Call History
                + iMessages
                + Calendar
                + Notes
                + File System
                + Maps Bookmarks/History/Directions
                + MAC Address
            - Recovers deleted data
            - Cannot access primary root file system
    + If phone is jailbroken:
        * Choose the **iPhone/iPad/iTouch Jailbroken (Logical)** plug-in
            - Only works with jailbroken iOS devices
            - Can access parts of the root file system
            - Recovers deleted data
            - Takes longer to backup
            - Paraben Device Seizure will automatically toggle iTunes connection throughout acquisition process
                + Don't manually connect to iTunes if disconnected

#### Evidence --- EXIF Data

Pictures taken with iPhone will contain datetime metadata and location metadata if location services was enabled.

Use an EXIF reader to view the metadata in a human-friendly format

iPhone will create both a `.jpg` and a `.thm` thumbnail image for each picture taken, both stored in the same folder

#### Evidence --- `.plist` Files

`.plist` = Information Property List file

An XML-like file which contains cache, history and configuration information

##### Google Maps property list
> maps/history.plist

`iPhone Device/file system/private/var/root/Library/maps/history.plist`
- Address/direction searches
    + Start/End address
    + Start/End latitude/longitude
    + Zoom level
    + Business name

> maps/route.plist

`./Library/maps/route.plist`
- Shows when the user has queried the map for directions

##### Network information property list
Shows router MAC addresses & IP addresses facilitating connection
> network.identification.plist

`iPhone Device/File System/Private/var/root/Library/preferences/system configuration/com.apple.network.identification.plist`

##### Cookies property list
Website history
> cookies/cookies.plist

`iPhone Device/File System/private/var/root/library/cookies/cookies.plist`

##### Bookmarks property list
> safari/bookmarks.plist

`./safari/bookmarks.plist`

#### Evidence --- Email

Perform a keyword search of `.html`
> mail/envelope Index

Also look in the envelope index file: `iPhone device/file system/private/var/root/Library/mail/envelope Index`

#### Evidence --- Autocomplete words data
> Keyboard/dynamic-text.dat

`iPhone device/file system/private/var/root/Library/Keyboard/dynamic-text.dat`

#### Evidence --- Notes
> notes.db

`iPhone Device/File System/private/var/root/Library/notes.db`

#### Evidence --- Voicemail
> voicemail/voicemail.db

`./Library/voicemail/voicemail.db`

#### Evidence -- Passwords

`iPhone Device/File System/Private/etc/passwd` has all the passwords

Encrypted using DES algorithm, can be cracked

#### Evidence --- iTunes desktop sync

`.MDBACKUP` files
- Can be imported into Paraben Device Seizure

- Photos
- Music
- Call logs
- Contacts & Calendar
    + Synchronized with:
    + Outlook
    + Outlook Express
    + Entourage
    + Yahoo!
- Email
- Bookmarks
- Serial Number
- IMEI
- CCID
- iTunes connection DateTime

#### Evidence --- Was an iPhone connected to this computer?

`C:/.../AppData/Apple Computer/iTunes`

## iOS Security

- iOS = Mac OS X Lite
- ARM processor
- Secure Boot Chain
- Hardware device keys
- Application Code Signing