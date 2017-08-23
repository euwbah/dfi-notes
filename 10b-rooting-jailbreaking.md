# 10b. Rooting, Jailbreaking

Escape restrictions:
- Cannot sideload[^1] \(iOS only)
- Cannot act as root user
- Code signing
- System config, overclocking, etc..

### Rooting vs. Jailbreaking vs. Unlocking

*"Rooting"* (Android):
- Can act as `root` user (i.e. can `su`)
- No need to root to sideload<sup><a href="#sideloading">1</a></sup>

*"Jailbreaking"* (iOS/Windows Surface RT):
- Requires exploiting software/hardware to modify OS settings
- Once jailbroken, privileged access and sideloading will be enabled
- Will still function normally (App Store, make calls...) contrary to myths

*"Unlocking"* (iOS):
- Requires jailbroken iOS
- By right only able to be done by the telco/carrier
    + Requires entering a special code
- Will allow the iPhone to be used with other telcos (i.e. contract-free iPhone)
- Illegal in US

### Motivations

End user motivation:
- More application sources (pirated software)
- Remove bloatware
- Access/modify restricted hardware components

Administrator motivation:
- Application binary collection for analysis
- Runtime analysis of software
- Filesystem monitoring/profiling
- Penetration testing targets
- To screenshot

### Risks

Production devices shouldn't be rooted/jailbroken:
- 3rd party tools malicious?
- Warranty voiding
- Bricking
- Performance issues
- EULA violation

Perform rooting/jailbreaking on test devices to check if it is ok to proceed.

### Tools

iPhone:
- JailbreakMe
- Redsn0w
- Evasi0n

Android:
- adb
    + drivers
    + scripts
    + `superuser.apk`
- z4root
- SuperOneClick (requires adb)
- Flashing custom ROM (and also recovery ROM in event of explosion)
- Motochopper

<a name="sideloading"><sup>1</sup></a>: Sideloading = loading apps not on official app store

