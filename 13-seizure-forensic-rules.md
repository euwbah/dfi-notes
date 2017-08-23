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

Use small Faraday cages to store devices while in transit/in the lab
    - Homemade (empty paint/arson can)
    - Paraben's Wireless StrongHold Bag Reusable/Single Use
    - Paraben's Tabletop StrongHold

### Rule 3: **Gather Cables & Accessories**

- Don't just take the device
    + Also collect
        * SIM Cards
        * Belt Clips
        * Chargers
        * Cradles
        * Computers the mobile device was connected to (iTunes backup!)
        * Encryption Keys
        * Additional storage (microSD/SD)
        * Wearables
    + Some obscure devices may be out-of-service and phone accessories/charger peripherals may be out of production or just hard to find

### Rule 4: **Work in a Controlled Environment**

Best case scenario: The device stays in a Faraday environment from beginning to end

Can either use a "Desktop" Faraday lab, or an actual Faraday Room, or even a TEMPEST facility


### Legal considerations

- Normally okay to search and retrieve data on seized devices (check with local District Attorney)
- If in doubt, warrant it out!