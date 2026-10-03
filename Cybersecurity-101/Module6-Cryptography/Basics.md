### Intro
- Cryptography lays the foundation for our digital world. While networking protocols have made it possible for devices spread across the globe to communicate, cryptography has made it possible to trust this communication.

### Importance
- Cryptography’s ultimate purpose is to ensure secure communication in the presence of adversaries.The term secure includes confidentiality and integrity of the communicated data. 
- **Cryptography can be defined as the practice and study of techniques for secure communication and data protection where we expect the presence of adversaries and third parties.**
-  When handling credit cards, organizations must follow and enforce the**Payment Card Industry Data Security Standard (PCI DSS)**. The PCI DSS ensures a minimum level of security to store, process, and transmit data related to card credits. 
- Example laws and regulations that should be considered when handling medical records include **HIPAA (Health Insurance Portability and Accountability Act)** and **HITECH (Health Information Technology for Economic and Clinical Health) in the USA**, **GDPR (General Data Protection Regulation) in the EU, DPA (Data Protection Act) in the UK**. 
- Although the list is not exhaustive, it gives an idea about the legal requirements that healthcare providers should consider depending on their country. These laws and regulations show that cryptography is a necessity that should be present yet usually hidden from direct user access.

# Plaintext to Ciphertext
- Plaintext is the original, readable message or data before it’s encrypted. It can be a document, an image, a multimedia file, or any other binary data.
- Ciphertext is the scrambled, unreadable version of the message after encryption. Ideally, we cannot get any information about the original plaintext except its approximate size.
- Cipher is an algorithm or method to convert plaintext into ciphertext and back again. A cipher is usually developed by a mathematician.
- Key is a string of bits the cipher uses to encrypt or decrypt data. In general, the used cipher is public knowledge; however, the key must remain secret unless it is the public key in asymmetric encryption. We will visit asymmetric encryption in a later task.
- Encryption is the process of converting plaintext into ciphertext using a cipher and a key. Unlike the key, the choice of the cipher is disclosed.
- Decryption is the reverse process of encryption, converting ciphertext back into plaintext using a cipher and a key. Although the cipher would be public knowledge, recovering the plaintext without knowledge of the key should be impossible (infeasible).

#### Caesar Cipher
- Cryptography’s history is long and dates back to ancient Egypt in 1900 BCE. However, one of the simplest historical ciphers is the Caesar Cipher from the first century BCE. The idea is simple: shift each letter by a certain number to encrypt the message.

- Consider the following example:

Plaintext: TRYHACKME
Key: 3 (Assume it is a right shift of 3.)
Cipher: Caesar Cipher
We can easily figure out that T becomes W, R becomes U, Y becomes B, and so on. Once we reach Z, we start all over, as shown in the figure below. Consequently, we get the ciphertext of WUBKDFNPH.
-  However, if someone gives you a ciphertext and tells you that it was encrypted using Caesar Cipher, recovering the original text would be a trivial task as there are only 25 possible keys. The English alphabet is 26 letters, and shifting by 26 will keep the letter unchanged; hence, 25 valid keys for encryption with Caesar Cipher.
-  Consequently, by today’s standards, where the cipher is publicly known, Caesar Cipher is considered insecure.

#### Encyption Types
The two main categories of encryption are **symmetric** and **asymmetric**.

### 1. Symmetric Encryption
Symmetric encryption, also known as symmetric cryptography, uses the same key to encrypt and decrypt the data.
-  Keeping the key secret is a must; it is also called **private key cryptography**. Furthermore, communicating the key to the intended parties can be challenging as it requires a secure communication channel. Maintaining the secrecy of the key can be a significant challenge, especially if there are many recipients. The problem becomes more severe in the presence of a powerful adversary.
- Examples of symmetric encryption are DES (Data Encryption Standard), 3DES (Triple DES) and AES (Advanced Encryption Standard).
   1. DES was adopted as a standard in 1977 and uses a 56-bit key. With the advancement in computing power, in 1999, a DES key was successfully broken in less than 24 hours, motivating the shift to 3DES.
   2. 3DES is DES applied three times; consequently, the key size is 168 bits, though the effective security is 112 bits. 3DES was more of an ad-hoc solution when DES was no longer considered secure. 3DES was deprecated in 2019 and should be replaced by AES; however, it may still be found in some legacy systems.
   3. AES was adopted as a standard in 2001. Its key size can be 128, 192, or 256 bits.

### 2. Asymmetric Encryption
Unlike symmetric encryption, which uses the same key for encryption and decryption, asymmetric encryption uses a pair of keys, one to encrypt and the other to decrypt, as shown in the illustration below. 
- To protect confidentiality, asymmetric encryption or **asymmetric cryptography** encrypts the data using the public key; hence, it is also called **public key cryptograph**y.
- Examples are RSA, Diffie-Hellman, and Elliptic Curve cryptography (ECC). The two keys involved in the process are referred to as a public key and a private key. Data encrypted with the public key can be decrypted with the private key. The private key needs to be kept private, hence the name.
- Asymmetric encryption tends to be slower, and many asymmetric encryption ciphers use larger keys than symmetric encryption. 
- For example, RSA uses 2048-bit, 3072-bit, and 4096-bit keys; 2048-bit is the recommended minimum key size. Diffie-Hellman also has a recommended minimum key size of 2048 bits but uses 3072-bit and 4096-bit keys for enhanced security. 
- On the other hand, ECC can achieve equivalent security with shorter keys. For example, with a 256-bit key, ECC provides a level of security comparable to a 3072-bit RSA key.

**Asymmetric encryption is based on a particular group of mathematical problems that are easy to compute in one direction but extremely difficult to reverse. In this context, extremely difficult means practically infeasible. For example, we can rely on a mathematical problem that would take a very long time, for example, millions of years, to solve using today’s technology.**

- Overall: Alice and Bob are fictional characters commonly used in cryptography examples to represent two parties trying to communicate securely. Symmetric encryption is a method in which the same key is used for both encryption and decryption. Consequently, this key must remain secure and never be disclosed to anyone except the intended party. Asymmetric encryption is a method that uses two different keys: a public key for encryption and a private key for decryption.

### Basic Math
- To demonstrate some basic algorithms, we will cover two mathematical operations that are used in various algorithms:
    1. XOR Operation
    2. Modulo Operation

1. XOR Operation

- XOR, short for “exclusive OR”, is a logical operation in binary arithmetic that plays a crucial role in various computing and cryptographic applications. In binary, XOR compares two bits and returns 1 if the bits are different and 0 if they are the same, as shown in the truth table below. This operation is often represented by the symbol ⊕ or ^.

| **A** | **B** |**A ⊕ B** |
| :---- | :---- | :-------- |
| 0     | 0     | 0         |
| 0     | 1     | 1         |
| 1     | 0     | 1         |
| 1     | 1     | 0         |


| **Property**    | **Meaning**                 |
| --------------- | --------------------------- |
| **Self-XOR**    | `A ⊕ A = 0`                 |
| **XOR with 0**  | `A ⊕ 0 = A`                 |
| **Commutative** | `A ⊕ B = B ⊕ A`             |
| **Associative** | `(A ⊕ B) ⊕ C = A ⊕ (B ⊕ C)` |

XOR as Symmetric Encryption
P = Plaintext
K = Secret Key
C = Ciphertext

Encryption:
```
C = P ⊕ K
```

Decryption:
```
C ⊕ K
= (P ⊕ K) ⊕ K
= P ⊕ (K ⊕ K)
= P ⊕ 0
= P
```
So, the same key K is used to encrypt and decrypt the data.
In practice, the key needs to be as long as the plaintext for this basic XOR approach.

2. Modulo Operation
- Another mathematical operation we often encounter in cryptography is the modulo operator, commonly written as % or as mod. The modulo operator, X%Y, is the remainder when X is divided by Y. In our daily life calculations, we focus more on the result of division than on the remainder. The remainder plays a significant role in cryptography.
- A few examples:
    1. 25 % 5 = 0 because 25 divided by 5 is 5, with a remainder of 0, i.e., 25 = 5 × 5 + 0
    2. 23 % 6 = 5 because 23 divided by 6 is 3, with a remainder of 5, i.e., 23 = 3 × 6 + 5
- An important thing to remember about modulo is that it’s not reversible. If we are given the equation x % 5 = 4, infinite values of x would satisfy this equation.

**The modulo operation always returns a non-negative result less than the divisor. This means that for any integer a and positive integer n, the result of a%n will always be in the range 0 to n − 1.**