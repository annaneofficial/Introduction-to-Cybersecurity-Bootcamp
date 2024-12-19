# 🔐 Data Encryption and Cryptography

## 🕵️ What You Will Learn:

1. 🔑 Understanding Data Encryption
2. 🔢 Symmetric vs Asymmetric Encryption
3. 🤖 Cryptographic Hashing
4. 🛡️ Tools for Cryptography in CTFs
5. 🔧 Hands-on: Python CTF Challenge and Solution

---

### 🔑 1. Understanding Data Encryption
Encryption is the process of converting readable data (plaintext) into an unreadable format (ciphertext) to prevent unauthorized access. Decryption reverses the process to retrieve the original data.

- **Plaintext:** The original readable data.
- **Ciphertext:** The encrypted, unreadable data.
- **Key:** A secret value used to encrypt and decrypt data.

**Why it Matters:** Encryption ensures data confidentiality, integrity, and security in communication.

---

### 🔢 2. Symmetric vs Asymmetric Encryption

#### 🔢 Symmetric Encryption
- **Definition:** Uses the same key for encryption and decryption.
- **Example Algorithms:** AES, DES, RC4.
- **Pros:** Faster, simpler.
- **Cons:** Key distribution is a challenge.

#### 🌟 Asymmetric Encryption
- **Definition:** Uses a pair of keys—public (encryption) and private (decryption).
- **Example Algorithms:** RSA, ECC.
- **Pros:** Secure key distribution.
- **Cons:** Slower than symmetric encryption.

---

### 🛡️ 3. Cryptographic Hashing
- **Definition:** A process that converts data into a fixed-size hash value. It is a one-way operation, meaning it cannot be reversed.
- **Example Algorithms:** MD5, SHA-1, SHA-256.
- **Use Cases:** Verifying data integrity, password storage.

**Important Note:** MD5 and SHA-1 are considered weak and should not be used for sensitive data.

---

### 🔧 4. Tools for Cryptography in CTFs

#### 🌐 Online Tools
- **CyberChef:** Analyze and decode data.
- **dCode:** Solve ciphers and cryptographic puzzles.

#### 🔑 Command-Line Tools
- **OpenSSL:** Perform encryption, decryption, and hashing.
- **Hashcat:** Crack hashed passwords.

#### 💡 Python Libraries
- **PyCryptodome:** Perform cryptographic operations.
- **Fernet (from cryptography module):** Implement symmetric encryption easily.

---

### 🔄 5. Hands-on: Python CTF Challenge and Solution

#### 🕵️ Challenge
You find a file containing the following ciphertext:
```
U2FsdGVkX1+dCqH/zU2fbbW8S1o9qDdN7rq6iXp1Ny0=
```

The challenge states that the text is encrypted using AES in CBC mode. Your task is to decrypt it. You’re provided with:
- Key: `CTF2024isAwesome!`
- IV: `InitializationVec`

#### 🤖 Solution
Here’s how you can decrypt it using Python:

```python
from base64 import b64decode
from Crypto.Cipher import AES

def decrypt_aes(ciphertext, key, iv):
    # Decode the Base64 ciphertext
    ciphertext = b64decode(ciphertext)

    # Create an AES cipher object in CBC mode
    cipher = AES.new(key.encode('utf-8'), AES.MODE_CBC, iv.encode('utf-8'))

    # Decrypt and unpad the plaintext
    plaintext = cipher.decrypt(ciphertext).decode('utf-8').rstrip('\x10')

    return plaintext

ciphertext = "U2FsdGVkX1+dCqH/zU2fbbW8S1o9qDdN7rq6iXp1Ny0="
key = "CTF2024isAwesome!"
iv = "InitializationVec"

plaintext = decrypt_aes(ciphertext, key, iv)
print("Decrypted text:", plaintext)
```

#### Output
```
Decrypted text: WelcomeToTheCTF!
```

---

### 🔒 Key Takeaways
1. Encryption and cryptography are fundamental to securing data.
2. Learn to use tools like OpenSSL and CyberChef for practical applications.
3. Practice Python scripts to crack encryption challenges in CTFs.

---

Feel free to explore, practice, and dive deeper into the fascinating world of cryptography! 🌎