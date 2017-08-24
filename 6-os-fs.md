# 6a. OS & File systems

### Boot sequence

**Complementary Metal Oxide Semiconductor**:
- Stores system configuration & date when no power is supplied

**Basic Input/Output System** / **Extensible Firmware Interface** (ROMs):
- Contains programs that perform IO at hardware level

Configure CMOS/BIOS/UEFI settings to boot from the forensic disk

Important to boot from the forensic disk to ensure that the main suspect source disk isn't altered 

## Microsoft File Structures

- Sectors are grouped to form **clusters**
    + Each cluster can be from 512 bytes (1 sector) to 32,768 (64 sectors) big
    + Combining sectors reduces overhead of reading & writing files to disk

**Logical addresses**: Cluster numbers (Starts at 0 in NTFS, 2 in FAT)
**Physical addresses**: Sector numbers

### Partitions

Partition = logical drive

Windows have 3 primary partitions + 1 extended partition containing >= 1 logical drive

Partition table contains addresses of first sectors of each partition and number of sectors in each partition

First partition table entry is at `0x1BE`, second at `0x1CE` and so on...

### FAT Disks

FAT = File Allocation Table

FAT16, FAT32, exFAT (Xbox)

Allocating disk space by clusters results in **drive slack**

Drive slack = **RAM slack** + **File slack**

Larger cluster size = less fragmentation

Deleting FAT files:

`0xE5` replaces the first letter of the filename
FAT file chain set to 0
Data in the file remains in disk -- **unallocated disk space**

### NTFS Disks

- Introduced with windows NT

#### Improvements over FAT

- more information (metadata)
- more control over files and folders
- journaling file system
- Much less file slack space
- Unicode

#### Filesystem

First data set is the **Partition Boot Sector**
followed by **Master File Table**

Master File Table contains metadata of all files on the disk
- First 15 records are reserved for system files
- Each record is 1024 bytes in size
- A field in the record is known as an **attribute ID**

Even though the Master File Table's contents is known as "metadata", only 512 bytes of the 1024 bytes in each record is actually used for metadata, the other 512 bytes can be used to store files less than 512 bytes in size. These types of files are known as **resident files**

(In NTFS, everything, even file contents, is metadata)

If the file is > 512 bytes, the MFT record provides **data runs** (similar concept to an `ext4` *'Extent'*) to the ranges of clusters of which makes up the file's contents. These types of files are known as **non-resident files**.

Assigned cluster numbers are called **Logical Cluster Numbers**, Logical Cluster Number addresses assigned to non-resident files becomes the file's **Virtual Cluster Number**

Important MFT header attribute fields (header is an attribute of an MFT entry):

`0x00`: The word `FILE` hex -- record delimiter <br>
`0x14`: Length of the header attribute <br>
`0x1C`-`0x1F`: MFT record size <br>
`0x32`-`0x33`: Update sequence array: last 2 bytes of the first sector of the MFT record

#### Alternate data streams

- Data can be appended to existing files
- Can be used as a tactic to hide data, whether intentional or by coincidence
- Alternate data streams become additional file attributes
- MFT shows alternate data streams

#### NTFS Encrypting File System

- Implements public-private key method of encrypting files, folders or volumes
- Works both locally on workstation, or on remote server
- A **recovery certificate** is generated and sent to the local administrator account
- The **Recovery Key Agent** uses the recovery certificate to recover the private key

#### Deleting files

- Plebian way of deleting => recycle bin
- `Ctrl+Del` or the MS-DOS `del` command will eliminate the file from the Master File Table the same way the File Allocation Table filesystem deletes a file
    + The data will marked unallocated still be on the disk until the data on the unallocated cluster has been overwritten with another allocated file

### Whole Disk Encryption

- It's a thing because of loss of **Personal identity information** & trade secrets

- Pre-boot authentication
- full/partial disk encryption with secure hibernation
- key management

To examine an encrypted drive, decrypt it first
- Bootable CD/USB drive prompts for a one-time passphrase

### Windows Registry

Registry = database storing hardware and software config. info, network connections, user pref., setup info.

Regedit / Regedt32 programs can be used to view the registry

### Startup tasks

Startup tasks will access some files upon start up

Checking when these files were last accessed will give a hint on when a suspect last used the computer should the computer be not powered-on during the investigation, assuming some dumb idiot didn't turn the computer on during the data acquisition itself.

Windows Vista or later:

boot process uses the **Boot Configuration Data store** (`bcdedit`)
- Contains boot loader executable that initiates the system's bootstrap process
- replaces Windows XP `boot.ini` file

Startup files to check:
- `Bootmgr.exe`
- `Winload.exe`
- `Winresume.exe`

Windows XP:

Startup files to check:
- `NTLDR`
- `boot.ini`
- `ntoskrnl.exe`
- `bootvid.dll`
- `bootSect.dos`
- `NTDetect.com`
- `Pagefile.sys`

