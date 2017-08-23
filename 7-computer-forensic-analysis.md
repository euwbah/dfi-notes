# 7. Digital Forensics Analysis and Validation
### ... specifically analysis only

#### What data to collect?

**Scope creep**: when an investigation expands beyond original expectations

#### Steps to collect data:

1. Used recently wiped/reformatted virus-free target drives
2. Note suspect's computer hardware & condition
3. Remove original drive and check date & time values in system's CMOS
4. Record how data was acquired
5. Process drive's contents methodically and logically
6. List all folders and files on the image/drive
7. Examine contents of all data files in all folders
8. Recover file contents for all password-protected files
9. Identify function of every executable file that doesn't match expected hash values of the original executable with the same name
10. Maintain control of all evidence and findings

### OSForensics

OSForensics performs forensics analysis on
- FAT12/16/32
- NTFS
- HFS+/HFSX
- ext2/4

Can use search terms to find evidence

Works on differing types of image formats

### Data-hiding techniques

Using the OS:
- Changing file extensions
    + Forensics tools can compare file header signature with the file extension
- Hidden file
- Hiding entire partitions
    + Using the `diskpart remove <drive letter>` command will remove the partition from view in the File Explorer
    + `diskpart assign <drive letter>` will restore it
    + hidden partitions can be detected by forensics tools or by accounting for disk space per partition
- Marking Bad Clusters
    + Using Norton DiskEdit to flag clusters in FAT file systems as bad so the OS considers them unusable
    + Need to remedy by changing the flag back to "good cluster" using a disk editor

Using third party tools:
- Bit shifting
- Steganography
    + Many freeware / shareware tools exist to conceal/scramble file information
- Encryption
    + Need to supply password/passphrase to decrypt
    + Password cracking tools:
        * Last Bit
        * AccessData PRTK
        * ophcrack
        * John The Ripper
        * Passware
    + Attack types:
        * Brute-force
        * Dictionary
        * Rainbow table
    + Salted passwords makes cracking passwords more difficult