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

