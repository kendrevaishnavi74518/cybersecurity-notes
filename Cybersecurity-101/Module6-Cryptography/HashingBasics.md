
### Intro
A hash value is a fixed-size string or characters that is computed by a hash function. A hash function takes an input of an arbitrary size and returns an output of fixed length, i.e., a hash value.

#### Hash Functions
- Hash functions are different from encryption. There is no key, and it’s meant to be impossible (or computationally impractical) to go from the output back to the input.

- A hash function takes some input data of any size and creates a summary or digest of that data. The output has a fixed size. It’s hard to predict the output for any input and vice versa. 
- Good hashing algorithms will be relatively fast to compute and prohibitively slow to reverse, i.e., go from the output and determine the input. 
- Any slight change in the input data, even a single bit, should cause a significant change in the output.

- The output of a hash function is typically raw bytes, which are then encoded. Common encodings are base64 or hexadecimal. md5sum, sha1sum, sha256sum, and sha512sum produce their outputs in hexadecimal format. Remember that hexadecimal format prints each raw byte as two hexadecimal digits.

#### Why is hashing important?
- Hashing plays a vital role in our daily use of the Internet. Like other cryptographic functions, hashing remains hidden from the user. Hashing helps protect data’s integrity and ensure password confidentiality.

-  In fact, as per good security practices, a server does not record your password; it records the hash value of your password. 
- Whenever you want to log in, it will calculate the hash value of the password you submitted with the recorded hash value. Similarly, when you log into your computer, hashing plays a role in verifying your password. 


#### Hashing Collision
- A hash collision is when two different inputs give the same output. Hash functions are designed to avoid collisions as best as possible. 
- Hash functions are designed to prevent an attacker from being able to create, i.e., engineer, a collision intentionally. 
- However, because the number of inputs is practically unlimited and the number of possible outputs is limited, this leads to a pigeonhole effect.
- Example, if a hash function produces a 4-bit hash value, we only have 16 different hash values. The total number of possible hash values is 2^number_of_bits.The probability of a collision is relatively very high.


#### Pigeonhole Effect
- The **pigeonhole effect** states that when the number of items (pigeons) is greater than the number of containers (pigeonholes), some containers must hold more than one item.
- A hash function has a fixed number of possible output values, but it can accept inputs of any size.
- Since there are more possible inputs than outputs, some different inputs will inevitably produce the same hash value.
- This is known as a **collision**.
- For example, if there are 21 pigeons and 16 pigeonholes, some pigeons must share the same pigeonhole.
- A good hash function ensures that the probability of a collision is negligible.


- MD5 and SHA1 have been attacked and are now considered insecure due to the ability to engineer hash collisions. 
- However, no attack has yet given a collision in both algorithms simultaneously, so if we compare the MD5 and SHA1 hash, you will see that they’re different. 
- Due to these, you shouldn’t trust either algorithm for hashing passwords or data.
