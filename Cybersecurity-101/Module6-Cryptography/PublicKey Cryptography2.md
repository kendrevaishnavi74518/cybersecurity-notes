## SSH
- ssh-keygen is the program usually used to generate key pairs.

1) DSA (Digital Signature Algorithm) is a public-key cryptography algorithm specifically designed for digital signatures.
2) ECDSA (Elliptic Curve Digital Signature Algorithm) is a variant of DSA that uses elliptic curve cryptography to provide smaller key sizes for equivalent security.
3) ECDSA-SK (ECDSA with Security Key) is an extension of ECDSA. It incorporates hardware-based security keys for enhanced private key protection.
4. Ed25519 is a public-key signature system using EdDSA (Edwards-curve Digital Signature Algorithm) with Curve25519.
5. Ed25519-SK (Ed25519 with Security Key) is a variant of Ed25519. Similar to ECDSA-SK, it uses a hardware-based security key for improved private key protection.
- `ssh-keygen -t ssh-key ed25519` : Generated a public key.
- If we used `-t rsa`, the resulting keys would have been much longer.

### SSH Private Keys
- As just mentioned, you should treat your private SSH keys like passwords. Never share them under any circumstances;
- It’s very important to mention that the passphrase used to decrypt the private key doesn’t identify you to the server at all; it only decrypts the SSH private key. The passphrase is never transmitted and never leaves your system.
- Using tools like **John the Ripper**, you can attack an encrypted SSH key to attempt to find the passphrase, highlighting the importance of using a complex passphrase and keeping your private key private.
- `ssh -i privateKeyFileName user@host` is how you specify a key for the standard Linux OpenSSH client.
- The ~/.ssh folder is the default place to store these keys for OpenSSH. The authorized_keys (note the US English spelling) file in this directory holds public keys that are allowed access to the server if key authentication is enabled.
-  By default on many Linux distributions, key authentication is enabled as it is more secure than using a password to authenticate. 
- Only key authentication should be accepted if you want to allow SSH access for the root user.

> Let’s say you have a website and want to use HTTPS. This step requires having a `TLS certificate`. You can get one from the various certificate authorities for an annual fee. Furthermore, you can get your own TLS certificates for domains you own using `Let's Encrypt` for free. If you run a website, it’s worth setting up and switching to HTTPS, as any modern website would do.

## PGP & GPG
- PGP stands for Pretty Good Privacy. It’s software that implements encryption for encrypting files, performing digital signing, and more. GnuPG or GPG is an open-source implementation of the OpenPGP standard.
- GPG is commonly used in email to protect the confidentiality of the email messages. Furthermore, it can be used to sign an email message and confirm its integrity.

> You would use `gpg --import backup.key` to import your key from backup.key
To decrypt your messages, you need to issue `gpg --decrypt confidential_message.gpg`

#### Conclusion
- Cryptography is the science of securing communication and data using codes and ciphers.
- Cryptanalysis is the study of methods to break or bypass cryptographic security systems without knowing the key.
- Brute-Force Attack is an attack method that involves trying every possible key or password to decrypt a message.
- Dictionary Attack is an attack method where the attacker tries dictionary words or combinations of them.