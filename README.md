# Arculus Recovery

Offline BIP39/BIP32 recovery and key-derivation tool with both:

- a browser-based interface in `Arculus_Recovery.html`
- a Python desktop/CLI version in `Arculus_Recovery.py`

This project is designed to run fully offline and uses only local computation.

## Features

- BIP39 mnemonic validation for 12-word and 24-word seeds
- Detailed validation output:
  - Word count
  - Wordlist validity
  - Entropy bits
  - Checksum bits
  - Checksum match
  - BIP-39 compliance
  - Root fingerprint
  - Keystore / seed format detection
  - Passphrase warning
  - BIP-39 seed (512-bit)
  - Master private key
  - Master chain code
- Address derivation for:
  - P2PKH
  - P2WPKH-P2SH
  - P2WPKH
  - P2TR (Taproot)
- Taproot support includes:
  - Bech32m addresses
  - BIP86 purpose detection (`m/86'/coin'/0'`)
  - Taproot internal public/private key data
  - Taproot tweak
  - Taproot output public/private key data
  - Taproot output key parity
- Multi-coin support:
  - Bitcoin
  - Litecoin
  - Dogecoin
- Encrypted seed export/import
- Hidden imported-seed workflow
- Press-and-hold seed reveal
- Inline root fingerprint display

## Security Notes

This tool is intended to be used offline.

Recommended usage:

1. Disconnect from the internet
2. Open the HTML file locally or run the Python script on a trusted machine
3. Never share your seed phrase, exported files, passwords, or derived private keys
4. Treat encrypted seed exports as sensitive backups

## Encrypted Seed Files

The project supports encrypted seed backup/export using the `.arc` file extension.

### Behavior

- `Encrypt/Export Seed` saves the active mnemonic into an encrypted `.arc` file
- `Import Seed` loads a `.arc` file back into the app
- Imported seeds remain hidden on screen
- Imported hidden seeds can still be validated and used for key derivation
- `Show Seed` temporarily reveals the hidden imported seed only while held down

### Compatibility

New `.arc` exports are designed to work in both:

- `Arculus_Recovery.html`
- `Arculus_Recovery.py`

## Files

- `Arculus_Recovery.html`  
  Browser-based offline recovery tool

- `Arculus_Recovery.py`  
  Python version with GUI and CLI support

- `test seed.txt`  
  Local test file in this workspace

## HTML Version

Open `Arculus_Recovery.html` directly in a browser.

### HTML Features

- Offline mnemonic validation
- Key and address derivation
- Export output
- Encrypt/export seed to `.arc`
- Import encrypted seed from `.arc`
- Hold-to-show hidden imported seed
- Root fingerprint display beside the Show Seed control

## Python Version

Run the Python script directly.

### Launch GUI

```bash
python Arculus_Recovery.py --gui
