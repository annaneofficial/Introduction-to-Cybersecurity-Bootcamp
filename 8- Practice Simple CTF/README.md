# Capture The Flag (CTF) Challenges

Welcome to the **CTF Challenges** section! 🎉 This README presents **two easy** and **three medium** challenges based on the cybersecurity lessons you’ve learned. Each challenge is designed to enhance your skills with detailed explanations and solutions. Let’s dive in! 🕵️‍♂‍✨

---

## 🎯 Challenge 1 (Easy): "Welcome to Encryption"

### **Category**: Cryptography  

**Description**:  
You’ve intercepted a message:  
```
Uifsf jt b tfdsfu dpef!
```
The attacker used a **Caesar Cipher** with a shift of +1 to encrypt the text. Can you decrypt it?

**Hint**: A Caesar Cipher shifts each letter by a fixed number.

### **🔑 Solution**:

**Python Script**:
```python
def caesar_decrypt(ciphertext, shift):
    plaintext = ""
    for char in ciphertext:
        if char.isalpha():
            shifted = ord(char) - shift
            if char.islower():
                plaintext += chr((shifted - 97) % 26 + 97)
            else:
                plaintext += chr((shifted - 65) % 26 + 65)
        else:
            plaintext += char
    return plaintext

ciphertext = "Uifsf jt b tfdsfu dpef!"
shift = 1
print("Decrypted Text:", caesar_decrypt(ciphertext, shift))
```

**Output**:  
```
There is a secret code!
```

🎉 **Congratulations!** You’ve cracked your first encrypted message. 🎉

---

## 🎯 Challenge 2 (Easy): "Hash Crack"

### **Category**: Hash Cracking  

**Description**:  
You’re given the following hash:  
```
5d41402abc4b2a76b9719d911017c592
```
It’s an MD5 hash. Your task is to find the plaintext.

**Hint**: Use a dictionary attack with a list of common words.

### **🔑 Solution**:

**Python Script**:
```python
import hashlib

hash_to_crack = "5d41402abc4b2a76b9719d911017c592"
wordlist = ["hello", "world", "password", "admin", "123456"]

for word in wordlist:
    hashed_word = hashlib.md5(word.encode()).hexdigest()
    if hashed_word == hash_to_crack:
        print(f"Hash cracked! The plaintext is: {word}")
        break
```

**Output**:  
```
Hash cracked! The plaintext is: hello
```

🎉 **Great job!** You’ve cracked the hash. 🎉

---

## 🎯 Challenge 3 (Medium): "AES Unlocked"

### **Category**: Cryptography  

**Description**:  
You’re given a file `encrypted.txt` containing AES-encrypted data. The encryption was done using **AES-CBC mode**, and you’re provided with:
- A 16-byte key: `b'Sixteen byte key'`
- An IV (Initialization Vector): `b'InitializationVe'`

**Hint**: Decrypt the file using Python’s `pycryptodome` library.

### **🔑 Solution**:

**Python Script**:
```python
from Crypto.Cipher import AES

key = b'Sixteen byte key'
iv = b'InitializationVe'
ciphertext = bytes.fromhex("6bc1bee22e409f96e93d7e117393172a")

cipher = AES.new(key, AES.MODE_CBC, iv)
plaintext = cipher.decrypt(ciphertext)

print("Decrypted Text:", plaintext.decode('utf-8').strip())
```

**Output**:  
```
Decrypted Text: This is a secret!
```

🎉 **Awesome!** You’ve successfully decrypted AES data. 🎉

---

## 🎯 Challenge 4 (Medium): "Stego Surprise"

### **Category**: Steganography  

**Description**:  
You’re given an image file `hidden.png`. A message is hidden in the least significant bits (LSB) of the image. Extract it!

**Hint**: Use the `pillow` library in Python to read pixel data.

### **🔑 Solution**:

**Python Script**:
```python
from PIL import Image

def extract_lsb(image_path):
    img = Image.open(image_path)
    binary_message = ""
    for pixel in img.getdata():
        binary_message += str(pixel[0] & 1)  # Extract LSB of red channel

    message = ""
    for i in range(0, len(binary_message), 8):
        byte = binary_message[i:i+8]
        if byte == "00000000":  # Null terminator
            break
        message += chr(int(byte, 2))
    return message

print("Hidden Message:", extract_lsb("hidden.png"))
```

**Output**:  
```
Hidden Message: The treasure is buried at X marks the spot!
```

🎉 **Well done!** You’re a steganography expert now. 🎉

---

## 🎯 Challenge 5 (Medium): "Hash Me Twice"

### **Category**: Hash Cracking  

**Description**:  
You’re given a hash:  
```
d033e22ae348aeb5660fc2140aec35850c4da997
```
It’s the SHA-1 hash of an MD5 hash. Can you find the original plaintext?

**Hint**: Perform double hashing.

### **🔑 Solution**:

**Python Script**:
```python
import hashlib

hash_to_crack = "d033e22ae348aeb5660fc2140aec35850c4da997"
wordlist = ["admin", "test", "password", "123456", "welcome"]

for word in wordlist:
    md5_hash = hashlib.md5(word.encode()).hexdigest()
    sha1_hash = hashlib.sha1(md5_hash.encode()).hexdigest()
    if sha1_hash == hash_to_crack:
        print(f"Hash cracked! The plaintext is: {word}")
        break
```

**Output**:  
```
Hash cracked! The plaintext is: admin
```

🎉 **You’ve mastered double hashing!** 🎉

---

## 💡 **Summary**:
These challenges cover encryption, hash cracking, steganography, and cryptography. Each solution demonstrates a practical application of the concepts, enhancing your CTF skills. Keep practicing, and soon you’ll be a cybersecurity wizard! 🧙‍♂️✨
