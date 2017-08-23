# 13. Mobile Device Seizure and Forensic Rules

### Rule 1: **Maintain Power**

- **KEEP POWER STATE**
    + If off, leave off;
    + If on, leave on
    + Prevents facing problems with encryption later on
        * PIN: 4 digit code, 3 mistypes before locking, changeable
        * PUK (PIN Unlocking Key): 8 digit code, 10 mistypes before locking, unchangeable
    + Keep the device charged

### Rule 2: **Block All Signals**

- **AIRPLANE MODE**
    + Block all signals (bluetooth, wifi, call/SMS, cellular data)
    + Protects from remote KILL commands
        * e.g. BlackBerry Enterprise
        * Can send a remote KILL command over a wireless network using BlackBerry Enterprise Server for Microsoft Exchange
    + It's possible to call for wiping of data/bricking/self-destruct remotely

- **FARADAY CAGE**
> “A charge only resided on the exterior of a
> charged conductor, and exterior charge had no
> influence on anything enclosed within a
> conductor. This is because the exterior charges
> redistribute such that the interior fields due to
> them cancel.”

    + Use small Faraday cages to store devices while in transit
        * Homemade (empty paint/arson can)
    