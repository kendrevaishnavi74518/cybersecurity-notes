## CIA Triad
Cybersecurity protects the systems,networks, & applications from attacks.
- Cybersecurity focuses on protecting 3 key aspects: 
   - Confidentiality
   - Integrity
   - Availability

## Confidentiality
- It ensures that sensitive data can only be accessed by authorized individuals.
- If confidentiality is not maintained, unauthorized individuals can access sensitive data, resulting in data loss, identity theft, financial loss or legal issues.

## Integrity
- It ensures that unauthorized individuals do not modify data.
- Without integrity, data can be altered, losing its originality.
- Unauthorized changes in data can sometimes lead to dangerous consequences.

## Availability
- It ensures that data & services are available to authorized users whenever required.
- Even a short period of downtime can have serious consequences on businesses, services & users.

## Cryptography

# Basics
1. Plaintext- A test message that can be easily read by the user.
2. Ciphertext- A scrambled version, that is unreadable, not supposed to make sense.Ciphertext should look like random nonsense to anyone who doesn't have the key.
3. Key - Secret component that controls how scrambling & unscrambling works.
4. Algorithm - Set of steps that explain how to usethe key on the message. Security comes from keeping the key secret.

**Encryption Process = Plaintext + encryption key --> Ciphertext**
**Decryption Process = Ciphertext + decryption key --> Plaintext**

## Symmetric Encryption — Lockbox Analogy

Think of encryption like a **locked box**:
- **Algorithm:** How the lock works; it is usually public.
- **Key:** The secret key used to lock and unlock the box.
- **Plaintext:** The original readable message.
- **Ciphertext:** The encrypted, unreadable message.

### How It Works

1. Alice writes a message (**plaintext**).
2. She encrypts it using an **encryption key**.
3. The message becomes **ciphertext**.
4. Alice sends the ciphertext to Bob.
5. Bob uses the **same key** to decrypt it and recover the plaintext.
-  **Symmetric Encryption = Same key is used to encrypt and decrypt.**

### Key Points
 - The **algorithm does not need to be secret**. The security comes from keeping the **encryption key secret**.
 - It is both fast & effcient.

## Caesar Cipher: Algorithm Plus Key
- Named after Julius Caesar.
- Example of symmetric encryption.
## How it works?
- Caesar cipher shiftes each letter in message by fixed no.of positions, known as **keys**.

- Caesar cipher is not secure & never used in real systems, as it is too easy to compromise & decrypt message.
- Here both sender & receiver need copy of the key.
- The key has to stay secret.

## Key Distribution Problem
Asymmetric encyption solves the key distribution problem.
- It uses 2 keys: Public & Private.
   - Public key: That anyone can access.
   - Private Key: Remains secret.

- Lets consider 2 users: U1 & U2
   - If U1 can encrypt something with U2's public key, then only U2's private key can decrypt it.
   - If U2 can encrypt something with U1's public key, then only U1's private key can decrypt it, primarily used for digital signs.

## Solution to Key Distribution Problem
1. **Bob** creates a **public key** and a **private key**.
2. Bob keeps the **private key secret** and shares the **public key**.
3. **Alice** gets Bob's public key and encrypts her message with it.
4. Alice sends the encrypted message to Bob.
5. **Bob uses his private key to decrypt the message.**

- **Public key = Used to encrypt**  
- **Private key = Used to decrypt**

- **The private key never needs to be sent over the network, solving the key distribution problem.**
<br>

- Most common use of asymmetric encryption is **HTTPS**.
How it works:
   1. Browser requests for website's public key.
   2. Website sends public key wrapped in a certificate.
   3. Browser & website use asymmetric encryption to agree on a shared secret(symmetric key), without anyone else being able to see it.
   4. They switch to fast symmetric encryption using that shared key, for rest of the session.
- This combo is sometimes called hybrid approach. 

## Certificate
 - Digital document that contains: someone public key, states to whom the key belongs.
 - A trusted authority digitally signs it, called Certificate Authority(CA).

 In practice, real systems use both:
   - Asymmetric encryption initiates a connection and securely shares a symmetric key.
   - Symmetric encryption takes over for the remainder of the session to efficiently handle data.

- This is how HTTPS, VPNs, and encrypted messaging apps all operate.
