# Cipher
AES Encryption and Decryption of Files
This project provides a simple and functional implementation of file encryption and decryption using AES (Advanced Encryption Standard) in CFB mode with PKCS7 padding. It's built with the cryptography library in Python.

Features:
Encrypts any file using a symmetric AES key

Decrypts encrypted files using the same key

Uses Base64 encoding to store encrypted output

Includes built-in example usage

Requirements:
-Python 3.x
-cryptography library
Install with:
pip install cryptography

Usage:
-Set the key
The AES key must be 16, 24, or 32 bytes long.
encryption_key = b'sfnt3iof2354dwe6'  # 16-byte key
-Provide input and output file paths
input_file = 'input.txt'
encrypted_file = 'encrypted_file.txt'
decrypted_file = 'decrypted_file.txt'
-Run encryption and decryption
encrypt_file(input_file, encrypted_file, encryption_key)
decrypt_file(encrypted_file, decrypted_file, encryption_key)

Security Notes:
The IV (Initialization Vector) is currently hardcoded as 16 zero bytes. For production, use a secure random IV and store it with the ciphertext.

Do not hardcode keys in real-world applications. Use secure key management practices.

License:
This project is open source and free to use under the MIT License.
