## RSA
- RSA is a public-key encryption algorithm that enables secure data transmission over insecure channels. With an insecure channel, we expect adversaries to eavesdrop on it.
- RSA is based on the mathematically difficult problem of factoring a large number. Multiplying two large prime numbers is a straightforward operation; however, finding the factors of a huge number takes much more computing power.

### RSA Calculation
1. Choose 2 prime numbers p & q, calculate 'n' by n = p*q.
2. With ϕ(n) = n − p − q + 1
> selects `e` such that e is relatively prime to ϕ(n);
    -  e × d = 1 mod ϕ(n)
    - The public key is (n,e) and the private key is $(n,d).
3. To encrypt:  y = x^e mod n
4. To decrypt:  x = y^d mod n

> The main variables for RSA in CTFs: p, q, m, n, e, d, and c. As per our numerical example:
   - p and q are large prime numbers
   - n is the product of p and q
   - The public key is n and e
   - The private key is n and d
   - m is used to represent the original message, i.e., plaintext
   - c represents the encrypted text, i.e., ciphertext

### Diffie - Hellman Key Exchange
- Key exchange aims to establish a shared secret between two parties. It is a method that allows two parties to establish a shared secret over an insecure communication channel without requiring a pre-existing shared secret and without an observer being able to get this key. Consequently, this shared key can be used for symmetric encryption in subsequent communications.

## Calculations:
1. Alice and Bob agree on the public variables: a large prime number p and a generator g, where 0 < g < p. 
2. Choose a private integer, 'a' & 'b'.
3. To calculate public key: A = g^a mod p
    - B = g^b mod p
4. Alice and Bob send the keys to each other.This is **key exchange**.
5.  Finally calculate the shared secret using the received public key and their own private key.

## Applications
- Diffie-Hellman Key Exchange is often used alongside RSA public key cryptography. 
- Diffie-Hellman is used for key agreement, while RSA is used for digital signatures, key transport, and authentication, among many others.
-  For instance, RSA helps prove the identity of the person you’re talking to via digital signing, as you can confirm based on their public key. This would prevent someone from attacking the connection with a man-in-the-middle attack.
- In brief, Diffie-Hellman and RSA are incorporated into many security protocols and standards to provide a comprehensive security solution.
