#5. Processing Crime and Incident Scenes
### ...Digital Evidence Control

------------------------------------------

> "Digital Evidence" refers to any information stored or transmitted in digital form

**Scientific Working Group on Digital Evidence (SWGDE)** sets standards for recovering, preserving, and examining digital evidence.

Follow practices consistent with the Federal Rules of Evidence -- attorneys will raise the issue of trustworthiness of digital evidence.

Most courts interpret digital evidence as secondhand / hearsay evidence

... with the exception of digital **Business-records**

Computer-**generated** vs Computer-**stored**

Computer-stored = user-generated --- must be shown to be authentic and trustworthy (e.g. Microsoft Word author metadata)

Computer-generated = by-default authentic if the program is shown to be functioning correctly

### Best Evidence Rule

Establishing digital evidence's trustworthiness originates from the "best evidence rule" for written documents:

1. Original writing, recording, or photograph is required
2. Allow duplicates if produced by the same impression as original

For digital evidence, this means that copies can be admitted in court as long as bit-stream copies of data are created and maintained properly.

## 5 Rules of evidence

1. Admissible by court
2. Authentic
3. Complete and unbiased
4. Reliable 
5. Believable by jury

### Private-sector incident guidelines

Companies should...
- display disclaimer stating that they reserve the right to inspect computing assets at will 
- have a policy statement on misuse of digital assets
- have a well-defined process explaining in what circumstances an investigation can be initiated
- have inventory databases of computer hardware & software

Upon discovery of incriminating evidence:

1. Determine whether incident meets elements of criminal law
2. Inform management
3. Stop investigation to ensure 4th Amendment restrictions on obtaining evidence isn't violated
4. Work with corporate attorney

Employer may be able to file a criminal complaint with police -- but employers usually are only interesting in enforcing company policy.

### Public-sector law enforcement crime scene guidelines

Rules of **search and seizure**

Only may search for and seize criminal evidence with **probable cause**

**Innocent information** -- unrelated information <br>
**Limiting phrase** -- separates innocent info from evidence <br>
**Plain view doctrine** -- doesn't really apply to digital evidence

### General guidelines

- Corporate assets might not be able to be taken offsite to the lab
    + Bring tools to conduct acquisition:
        * Initial-response field kit
        * Extensive-response field kit
- Keep a journal
- Secure the scene
    + _"Get lost"_
- Take video and still recordings of the area around the computer
- Check state of computers
    + Screen on?
    + Move mouse --> screen on?
    + Turn on monitor --> ?
- Don't cut electrical power
- Save data of all running applications
- Record all active windows / shell sessions
- Close applications and shut down computer (if to be taken to the lab)
- **Bag & tag evidence**
    + Collect & log all evidence
    + Tag it with:
        * Current date & time
        * Serial numbers
        * Unique features
        * Model
        * Name of person who collected it
    + Maintain 2 separate logs
    + Maintain constant control of the evidence & scene
    + Look for related information & devices:
        * Password books (passwords, PINs, bank accounts)
        * Documentation / Manuals
        * Software & Hardware
        * Backup media
        
### Documenting & Handling evidence in the lab

- Record all findings & steps to achieve them in a journal
    + Follow steps --- ensure reproducible results
- Maintain integrity of digital evidence
- Make multiple copies of image files
    + on CDs/DVDs (ideally)
    + Magnetic tapes
    + Super Digital Linear Tapes (SDLT)
        * Can be connected to workstation via SCSI card
- Store original media in evidence locker
- Run hashing algorithms on image files to ensure integrity
- Ensure chain of custody
    + Evidence custody form:
        * Identifies evidence
        * Identifies who has handled the evidence
        * Dates & Times when evidence was handled
        * Hash values of evidence or its contents
    + Restrict lab & evidence storage area access
    + Visitor sign-in roster
- May need to retain evidence indefinitely:
    + Ensure it is compliant with state laws
- Store electronic components in anti-static containers

### Types of hashes

A forensic **hashing algorithm** has 3 attributes:
- You can't predict hash value of a file or device
- No two hash values can be the same
- If anything changes in the file/device, hash value must change

**Cyclic Redundancy Check**
- Mathematical algorithm
- Not forensic algorithm

**Message Digest 5**
- Is forensic

**Secure Hash Algorithm**
- Is forensic
- Developed by National Institute of Standards and Technology


