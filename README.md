SignalKeyExtract - portable Signal Desktop key extractor


WHAT IT DOES
  Recovers the SQLCipher database key for Signal Desktop on Windows by
  unwrapping the DPAPI-protected OSCrypt key (Local State) and AES-256-GCM
  decrypting the encryptedKey in config.json. Prints the 64-char hex key and
  the PRAGMA lines to open sql\db.sqlite. Legacy plaintext keys are handled too.

HOW TO USE
  1. Copy this whole folder to a USB stick.
  2. On the target Windows machine, logged in as the Signal user,
     double-click Run-SignalKeyExtract.bat.
  3. Optionally type a case reference. The key prints to screen and a JSON
     report is written to this USB folder (signal_key_<HOSTNAME>.json).

REQUIREMENTS / NOTES
  * DPAPI is user-scoped: must run as the account that owns the Signal
    profile. Running as SYSTEM or a different admin will fail.
  * Read-only on the Signal profile. Source artefacts are SHA-256 hashed.
  * A bundled Python interpreter (python\) is included; nothing is installed
    on the target. Windows 10/11 x64 hosts only.
  

