# RSA Factoring

### Factorize all the things!
Factorize as many numbers as possible into a product of two smaller numbers.

#### Usage
```shell
factors <file>
```
- `<file>`: A file containing natural numbers to factor. One number per line.

#### Input Format
- Each line in the file contains a natural number greater than 1.
- There are no empty lines, and no spaces before or after the valid number.
- The file always ends with a new line.

#### Output Format
- Output format: `n=p*q`
- One factorization per line.
- `p` and `q` don’t have to be prime numbers.

#### Constraints
- You can work on the numbers of the file in the order of your choice.
- Your program should run without any dependency.
- Time limit: 5 seconds.

#### Example
```shell
$ cat tests/test00 
4
12
34
128
1024
4958
1718944270642558716715
9
99
999
9999
9797973
49
239809320265259
$ ./factors tests/test00
4=2*2
12=6*2
34=17*2
128=64*2
1024=512*2
4958=2479*2
1718944270642558716715=343788854128511743343*5
9=3*3
99=33*3
999=333*3
9999=3333*3
9797973=3265991*3
49=7*7
239809320265259=15485783*15485773
```
[rsa](./rsa)

### RSA Factoring Challenge

RSA Laboratories states that for each RSA number `n`, there exist prime numbers `p` and `q` such that `n = p × q`. The problem is to find these two primes, given only `n`.

This task is the same as the above task, except:
- `p` and `q` are always prime numbers.
- There is only one number in the files.

The goal is to determine how far you can go in less than 5 seconds.

#### Input Format
The input consists of text files containing RSA numbers. Each file contains one RSA number.

#### Output Format
For each RSA number, the program should output the prime factors `p` and `q` such that `n = p × q`.

#### Example
```shell
$ cat tests/rsa-1
6
$ ./rsa tests/rsa-1
6=3*2
```

```shell
$ cat tests/rsa-2
77
$ ./rsa tests/rsa-2
77=11*7
```

```shell
$ cat tests/rsa-15
239821585064027
$ ./rsa tests/rsa-15 
239821585064027=15486481*15485867
```

```shell
$ cat tests/rsa-16
2497885147362973
$ ./rsa tests/rsa-16
2497885147362973=49979141*49978553
```
[factors](./factors)

### Prime Factorization
Prime factorization is the process of finding the prime numbers that multiply together to give a particular composite number. It is a fundamental concept in number theory and plays a crucial role in cryptography, particularly in the RSA encryption algorithm.

###  (Rivest–Shamir–Adleman) 

RSA is a widely used public-key cryptography system that enables secure communication over insecure channels. It involves a pair of mathematically linked keys: a public key and a private key.

Here's a breakdown of RSA usage and its key components:

**Components:**

* **Public Key:** This key is freely distributed and can be known by anyone. It's used for encrypting messages or verifying digital signatures.
* **Private Key:** This key is kept secret by the owner and is used for decrypting messages encrypted with the corresponding public key or signing digital documents.

**Usages of RSA:**

1. **Secure Communication:**
    * **Encryption:** You can use the recipient's public key to encrypt messages. Only the corresponding private key can decrypt them, ensuring confidentiality.
    * **Digital Signatures:** You can use your private key to sign digital documents, verifying their authenticity and origin. The recipient can use your public key to validate the signature. This is essential for secure transactions and document verification.

2. **Key Exchange:**
    In some protocols, RSA can be used to establish a secure channel for exchanging symmetric keys. These symmetric keys are then used for bulk encryption/decryption due to their efficiency, while RSA secures the initial key exchange.

3. **Digital Rights Management (DRM):**
    RSA can be used to encrypt and control access to copyrighted digital content. The content is encrypted with a public key, and authorized users possess the corresponding private key to decrypt and access it.

4. **Secure Logins:**
    Some two-factor authentication systems use RSA. The initial login might involve a password, and the second factor could be a challenge-response system secured with RSA.

5. **Secure Shell (SSH):**
    SSH, a protocol for secure remote login, utilizes RSA for key exchange to establish an encrypted connection between client and server.

**Benefits of RSA:**

* **Confidentiality:** Ensures only authorized parties can access encrypted messages.
* **Authentication:** Verifies the identity of parties involved in communication (digital signatures).
* **Non-repudiation:** Provides proof that a message originated from a specific party (digital signatures).

**Limitations of RSA:**

* **Computational Cost:** Public-key cryptography like RSA is computationally more expensive than symmetric cryptography. It's typically used for key exchange or digital signatures, then symmetric encryption is used for bulk data encryption.
* **Key Management:** Securely storing and managing private keys is crucial. Losing a private key can compromise security.

Overall, RSA is a cornerstone of public-key cryptography and plays a vital role in securing online communication, transactions, and digital assets. 
