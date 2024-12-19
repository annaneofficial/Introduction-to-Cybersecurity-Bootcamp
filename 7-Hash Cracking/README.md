### Hash Cracking Tutorial

#### 🔥 **What Will You Learn?**  
1. 🌐 What is Hash Cracking?  
2. 🔑 Types of Hashing Algorithms  
3. 🛠️ Tools Used for Hash Cracking  
4. 🚀 Techniques for Hash Cracking  
5. 💻 Python Script Example for Hash Cracking  
6. 🧹 CTF Challenge: Hash Cracking  

---

### 🌐 **What is Hash Cracking?**  
Hash cracking is the process of reversing a hashed value back into its original plaintext form. It's commonly used in cybersecurity for penetration testing, password recovery, and CTF challenges.  

- Hashes are one-way functions that convert input data into a fixed-length string.  
- Examples include **MD5**, **SHA-1**, and **SHA-256**.  
- Hash cracking exploits weaknesses in the hashing algorithm or uses brute force techniques to recover the plaintext.

---

### 🔑 **Types of Hashing Algorithms**  

1. **MD5 (Message Digest 5)**  
   - 📋 Produces a 128-bit hash value.  
   - 🔓 Not secure; vulnerable to collision attacks.  

2. **SHA-1 (Secure Hash Algorithm 1)**  
   - 📋 Produces a 160-bit hash value.  
   - 🔓 Deprecated due to vulnerabilities.  

3. **SHA-256**  
   - 📋 Part of the SHA-2 family; produces a 256-bit hash value.  
   - 🔒 More secure but slower.  

4. **bcrypt**  
   - 📋 A password hashing algorithm with a salt.  
   - 🔒 Resistant to brute-force attacks.  

---

### 🛠️ **Tools for Hash Cracking**  

1. **Hashcat** 🐱  
   - A powerful GPU-based tool for cracking hashes.  
   - Supports a wide range of algorithms.  

2. **John the Ripper** 💪  
   - Open-source, CPU-based tool for password cracking.  
   - Great for wordlist-based attacks.  

3. **Hydra** 🐍  
   - Focuses on cracking authentication systems.  
   - Used for brute force attacks.  

4. **Online Hash Crackers** 🌐  
   - Websites like CrackStation and HashKiller for quick hash lookups.  

---

### 🚀 **Hash Cracking Techniques**  

1. **Dictionary Attack**  
   - Uses a precompiled list of possible passwords.  
   - 🛠️ Use tools like Hashcat or John the Ripper.  

2. **Brute Force Attack**  
   - Tries every possible combination of characters.  
   - Effective but time-consuming.  

3. **Rainbow Table Attack**  
   - Precomputed tables of hashes for common passwords.  
   - 🛠️ Can speed up cracking but requires significant storage.  

4. **Salting**  
   - Adding random data to hashes to defend against precomputed attacks.  

---

### 💻 **Python Script Example: Hash Cracking**  

#### 📜 Script: Crack MD5 Hashes Using a Dictionary  

```python
import hashlib

def crack_md5_hash(hash_to_crack, wordlist_file):
    with open(wordlist_file, 'r') as file:
        for word in file:
            word = word.strip()
            hashed_word = hashlib.md5(word.encode()).hexdigest()
            if hashed_word == hash_to_crack:
                return f"Password found: {word}"
    return "Password not found."

# Example usage
hash_value = "5f4dcc3b5aa765d61d8327deb882cf99"  # MD5 hash of "password"
wordlist_path = "wordlist.txt"  # Path to your wordlist file

result = crack_md5_hash(hash_value, wordlist_path)
print(result)
```  

#### 💡 Explanation:  
1. Load a wordlist containing possible passwords.  
2. Hash each word using MD5 and compare it to the provided hash.  
3. If a match is found, the plaintext password is revealed.  

---

### 🧹 **CTF Challenge: Hash Cracking**  

#### 🎩 Challenge:  
You’re given a hash: `5d41402abc4b2a76b9719d911017c592`  
Your task is to crack it using a dictionary attack.

#### 🔑 Solution:  
1. The hash is an MD5 hash.  
2. Use the provided Python script or Hashcat.  
3. Use the wordlist `rockyou.txt`.  
4. Result: The plaintext password is `"hello"`.  

---

### 🏁 **Conclusion**  
Hash cracking is an essential skill in penetration testing and CTF competitions. By understanding different algorithms, techniques, and tools, you can efficiently crack hashes and improve your cybersecurity skills.  

💻 Happy Cracking! 🚀
