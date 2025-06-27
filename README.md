AES File Encryption and Decryption (Python)

This script provides functions to securely encrypt and decrypt files using AES encryption with the Python `cryptography` library.

Features

- AES encryption in Cipher Feedback (CFB) mode
- PKCS7 padding for block alignment
- Base64 encoding for output files
- Simple file-based input and output

How It Works

- encrypt_file(input_file_path, output_file_path, key):
  Reads a plaintext file, pads it, encrypts using AES-CFB with a fixed IV, and writes the encrypted data (base64-encoded) to the output file.

- decrypt_file(input_file_path, output_file_path, key):
  Reads an encrypted file, decodes base64, extracts the IV, decrypts the ciphertext, removes padding, and writes the plaintext to the output file.

Usage Example

encryption_key = b'sfnt3iof2354dwe6'  # Must be 16 bytes for AES-128
input_file = 'input.txt'
encrypted_file = 'encrypted_file.txt'
decrypted_file = 'decrypted_file.txt'

encrypt_file(input_file, encrypted_file, encryption_key)
decrypt_file(encrypted_file, decrypted_file, encryption_key)

Notes

- The initialization vector (IV) is currently fixed as 16 zero bytes (b'\0' * 16). For real-world security, use a random IV for each encryption and store it with the ciphertext.
- The key must be 16 bytes long (AES-128). Adjust for AES-192 or AES-256 by changing the key length accordingly.
- Base64 encoding ensures encrypted files are text-friendly for storage or transfer.
- Requires the `cryptography` library (`pip install cryptography`).

License

MIT License

Author: Christopher Kelley
