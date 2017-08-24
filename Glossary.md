# This glossary only includes terms worth studying

## Forensics software file extensions
**`.E01`** -- EnCase / AccessData Forensics Tool Kit (FTK) images
**`.eve`** -- ProDiscover images
**`.AFF`** -- Advanced Forensics Format
**`.DD`**/**`.RAW`** -- Raw file formats
**`.dft`** -- ProDiscover project file

## 1. Intro to digital forensics

Fourth amendment

Case Law

Blotter

Digital Evidence First Responder

Digital Evidence Specialist

Affidavit

Evidence exhibits

Private-sector/public-sector

Bring your own device

Chain of custody

# 3a. Investigator's office & lab

Lab manager

Staff

Budget planning
Uniform Crime Report

Certs:
- International Association of Computer Investigative Specialists (IACIS) test
    + become a Certified Forensic Computer Examiner
- Certified Cyber Forensics Professional
- High-Tech Crime Network
	+ Certified Computer Crime Investigator
	+ Certified Computer Forensic Technician
- EnCase Certified Examiner Certification
- AccessData Certified Examiner Certification

Minimum Requirements

Visitor Badge

Secure evidence container
TEMPEST facilities

Audits

ATA (Advanced Technology Attachment)
IDE (Integrated Drive Electronics) aka PATA (Parallel ATA)
SATA (Serial ATA)
FireWire
USB
SCSI

# 3b. Current forensics tools

1. Acquisition
	- Physical data
	- Logical data
	- Raw data
	- Vendor specific / proprietary
	- Command-line
	- GUI
	- Remotely / On-site
	- Live
	- Static
	- RAM acquisition
2. Validation & Verification
	- file header metadata
	- file signature vs. file extension
	- hashing
		+ CRC-32
		+ MD5
		+ SHA-1/256/512
3. Extraction
	- Data viewing
	- Keyword searching
	- Decompressing
	- Carving
	- Decrypting
	- Bookmarking / tagging
4. Reconstruction
	- disk-to-image copy:
		+ Linux `dd` command
5. Reporting
	- Bookmarks, tags
	- Log reports
	- Generated reports

SMART
Helix 3
Kali Linux
Autopsy & Sleuth Kit

Workstation types:
- stationary
- lightweight
- portable

Forensics-dedicated workstations / hardware:
- F.R.E.D. unit
- ForensicPC hardware mounts

Write blocker

National Institute of Standards and Technology
- ISO 17025 -- criteria for testing items that have no current standards

ISO 5725 --- results must be repeatable and reproducible

National Software Reference Library
- Reference Data Set

Computer Forensics Examination Protocol

Digital Forensics Tool Upgrade Protocol

## 4. Data acquisition

Image file formats
* Raw
    - `.bin`
    - `.raw`
    - `.dd`
    - `.001`
    - `.img`
* Proprietary
    - `.E01` (EnCase)
    - `.eve`/`.cmp` (PD uncomp. / comp)
* Advanced Forensics Format
    - `.AFF`
    - `.AFD` (segmented)
    - `.AFM` (metadata)

disk-to-image file

disk-to-disk

logical acquisition / disk-to-data file

sparse acquisition

lossless compression is accepted

host protected area

BitLocker whole disk encryption

Drive jumpers

write-blocker

Software acquisition
- ProDiscover Basic
- AccessData Forensics ToolKit Imager Lite

LiveCD Boot
- Mini-WinFE

source drive - target drive

Remote acquisition
- ProDiscover Incident Response --- PD Server
    + "Pushing out"
    + Stealth mode
    + communicates over Secure Connection Protocol
- EnCase Enterprise
    + Hardware & software RAID support
- R-Tools R-Studio
    + communicates over Triple Data Encryption Standard (3DES) encryption

Validating Acquisitions
- Hashing
- Commercial forensics software bespoke validation
- Raw acquired disk images have no metadata --- manual validation

## 5. Digital Evidence Control

Scientific Working Group on Digital Evidence (SWDGE)

Business records

Computer-generated vs Computer-stored

Best evidence rule

1. Admissible
2. Authentic
3. Complete
4. Reliable
5. Believable

#### Private-sector:

- disclaimer
- inventory database
- policy statement

Discovery of incriminating evidence:
- criminal law
- inform management
- adhere to 4th amendment
- corporate attorney

#### Public sector:

probable cause

innocent information
limiting phrase
plain view doctrine

#### General guidelines when collecting evidence

Not able to take offsite? Initial/extensive response field kit <br>
Multiple journals <br> 
"Get lost" <br>
video <br> 
move mouse etc <br>
don't cut power <br>
save data of running applications <br>
record all active windows <br>
shut down

**Bag & tag**

Related information

How to document & handle evidence in the lab?

Types of hashes:
    - Cyclic Redundancy Check
    - Message Digest 5
    - Secure Hash Algorithm

## 6a. OS & File Systems

Complementary Metal Oxide Semiconductor

Basic Input/Output System

Extensible Firmware Interface

CMOS/BIOS/UEFI settings boot from forensic disk

Clusters

Logical (cluster) / Physical (sector) addresses

Partitions

Partition table `0x1BE`, `0x1CE`, `0x1DE`...

FAT = lots of drive slack (RAM slack + file slack)
First letter of file name `0xE5` &Sigma;

Partition boot sector

Master File Table

Master File Table header attribute fields:
`0x00`
`0x14`
`0x1C`-`0x1F`
`0x32`-`0x33`

Alternate Data Streams `asdf.txt:hidden_prog.exe`

Encrypting File System

Whole Disk Encryption
Personal identity information
pre-boot authentication
BitLocker

Windows Registry

Startup tasks

When was the computer last used

Boot Configuration Data store (`bcdedit`)

startup files:

Windows Vista or later:
`bootmgr.exe`
`winload.exe`
`winresume.exe`

XP:
`NTLDR`
`boot.ini`
`ntoskrnl.exe`
`bootSect.dos`
`NTDetect.com`
`Pagefile.sys`

## 7. Digital Forensics Analysis

scope creep

1. Recently wiped media
2. Note condition & hardware
3. Remove drive, check CMOS datetime
4. Record acquisition process
5. Process drive methodically and logically
6. List all folders/files
7. Examine everything
8. Recover password-protected content
9. Identify fishy executables
10. Maintain control of all evidence and findings

OSForensics search terms

#### Data obscuring techniques

Changing file extensions
    * file signature

Hidden file

`diskpart assign|remove <drive letter>`

Norton DiskEdit fake bad cluster

Bit-shifting

Steganography
    * JPHide/Seek
    * SNOW.EXE

Encryption

Password-cracking:
    * Last Bit
    * AccessData Password Recovery Tool Kit
    * ophcrack
    * John The Ripper
    * Passware
+ Brute-force
+ Dictionary
+ Rainbow table

Salting

## 10.b Rooting/Jailbreaking/Unlocking

KNOW THE DIFFERENCE

root = Android root access (sideloading doesn't need root on Android)
jailbreak = iOS root access + sideloading
unlocking = use other telco's on the iPhone (iPhones can be tied to a telco contract and will lock to that telco only)

sideloading = installing/loading apps from unofficial sources (e.g. pirated)

unlocking is illegal in the US

Risks:
- malicious 3rd party tools
- Warranty
- Bricking
- EULA

Tools:
- JailbreakMe
- Redsn0w
- Evasi0n

- adb
- z4root
- SuperOneClick
- Custom ROMs
- Motochopper

## 11. iOS Mobile Forensics & Data Types

Darwin (UNIX)

Partitions:
1. MBR
2. Apple_Free
3. Main OS Partition (HFSX)
4. Apple_Free
5. Data Partition

OS Layers:
1. Core OS
2. Core Services
3. Media Layer
4. Cocoa Touch

Main "root" directory:
`iPhone Device/File System/private/var/root/`

Directory structure:
`Applications/`
`Library/`
Other standard folders like on windows, just that instead of "Videos" it is called "Movies", also with the addition of "Public" and "Sites"

> iPhone/iPad/iTouch **Advanced vs. Jailbroken** (Logical) plug-in

Evidence sources:
- EXIF Image metadata
- `.plist` property list files (XML formatted data)
    + `maps/history.plist`
    + `maps/route.plist`
    + `network.identification.plist`
    + `cookies/cookies.plist`
    + `safari/bookmarks.plist`
- `mail/envelope Index`
- `Keyboard/dynamic-text.dat`
- `notes.db`
- `voicemail/voicemail.db`
- `iPhone Device/File System/private/etc/passwd`
    + passwords encrypted using DES, can be cracked
- iTunes backup files on computer `.MDBACKUP` files
- Can check if an iOS device was connected to a computer by looking inside `Apple Computer/iTunes/` directory of the respective application data folder

iOS Security:
- iOS similar to Mac OS X
- Secure boot chain
- Hardware device keys
- Application Code Signing

# 12. Android Forensics & Data Types

Dalvik Virtual Machine

`.dex` Dalvik executables

Acquisition:
- Allow apps from unknown sources
- Enable USB debugging
- `AndroidService.apk` => `/data/local/tmp` => `com.paraben.service`
- auto uninstall & remove --- every back to normal

> Android (**Logical/Physical**) plug-in

Logical acquisition:
- Data types:
    + Browser history
    + Calendar
    + Call History
    + Contacts
    + File System
    + Media Store
    + MMS History
    + Settings
    + SMS History
- Logical folders/files acquired:
    + `dalvik-cache/`
    + `anr/` (debug/thread info)
    + `app/` (`.apk` files)
    + `data/`
    + `misc/`
    + `system/packages.xml`
    + `checkin.db`

Physical acquisition:
- Data types:
    + Flash Storage
    + Memory Card
- Basically acquire everything on the selected storage media as-is

Security:
- Linux kernel <--> OS
- App sandbox
- Secure interprocess communication
- Application signing
- Permissions API

## 13. Mobile Device Seizure & Forensic Rules

THE RULES:
1. Maintain Power
    - PIN
    - PUK
2. Block All Signals
    - Faraday Cage
    - Paraben Wireless StrongHold Bag (Reusable/Single Use)
    - Paraben Tabletop StrongHold
3. Peripherals
    - SIM Cards
    - Belt Clips
    - Chargers
    - Cradles
    - Computers
    - Encryption Keys / Password books
    - Additional Storage
    - Wearables
4. Controlled environment
    - Best case scenario:
        + Device is in a Faraday environment from start to finish

Legal Considerations:
> In in doubt, warrant it out!

