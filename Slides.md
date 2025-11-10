---
marp: true
transition: fade-out
theme: default
class: 
  - invert
paginate: true
backgroundColor: #000
style: |
  .container{
    display: flex;
  }
  .col{
    flex: 1;
  }
  img[alt~="center"] {
    display: block;
    margin: 0 auto;
    vertical-align: middle;
  }
  section.lead {
    text-align: center;
    color: white
  }
---

![bg left](images/Foundation.jpg)
# **PKI Foundations for Security Pros**

## Jake Hildreth
## [jakehildreth.com](https://jakehildreth.com/)

Anti-Cast, 2025-11-12

---
![bg right:40% 110%](images/Family.png)
# `Get-ADUser -Identity ‘Jake Hildreth’`
- Husband, Dad, Recovering Sysadmin
* Principal Security Consultant @ Semperis
* Open-source Toolmaker:
Locksmith, BlueTuxedo, PowerPUG!
* Microsoft MVP:
PowerShell + Identity & Access

---

# Agenda
<div class="container">
<div class="col">

* History & Goals
* Encoding vs. Encryption
* Symmetric Encryption
* Asymmetric Encryption
* Hashing Functions
</div>

<div class="col">

* Signing
* Certificates
* Public Key Infrastructute (PKI)
* Real-World Uses
</div>

---
<!-- _class: lead -->
# **History**
In the beginning was the word...

---

![bg right](images/BigBang.svg)
# **History**
In the beginning was the **pass**word...

---

<div class='container'>
<div class='col'>

## Antiquity
* 1900 BCE: Non-Standard Hieroglyphs
* 1500 BCE: Clay Tablets
* 600 BCE: Hebrew Scholars
* 400 BCE: Polybius Square
* 300 BCE: Kama Sutra
* 75 BCE: Caesar
</div>
<div class='col'>

## Medieval
* 750-800 CE: Arabic Scholars
* 800-1100 CE: English Scribes
* 1400 CE: Arabic Scholars
* 1508 CE: Tabula Recta
* 1626 CE: Antoine Rossignol
</div>

--- 

<div class='container'>
<div class='col'>

## Pre-WWII
* Focus on Cryptanalysis
* Many Medieval Systems Broken
* First Cryptographic Machines
* First One Time Pad
</div>
<div class='col'>

## WWII
* Allies:
  - TypeX, SIGABA, Lacida
* Axis:
  - Enigma, Purple, SG-41
</div>

---

## Modernity

<div class='container'>
<div class='col'>

* Claude Shannon
* Data Encryption Standard (DES)
* Diffie-Hellman (DH)
* Rivest, Shamir, Adelman (RSA)
* Message Digest Algorithms (MD*)

</div>
<div class='col'>

* Digital Signature Algorithm (DSA)
* Secure Hash Algorithms (SHA)
* Elliptic Curve Cryptography (ECC)
* Advanced Encryption Standard (AES)
* Post-Quantum Cryptography (PQC)
</div>

---
<!-- _class: lead -->
![bg left](images/GoalPosts.jpg)
# **Goals of Cryptography**

--- 

![bg right:41% 100%](images/Confidential.jpg)
# Confidentiality
### Ensures a message is only readable by its intended recipient.

---

![bg left](images/Integra.jpg)
# Integrity
### Ensures a message has not been tampered with or changed.

---

![bg right](images/.jpg)
# Non-Repudiation
### Ensures an author cannot refute authorship of a message.

---

![bg left:40% 110%](images/Popeye.jpg)
# Authentication
### Provides proof an author of a message is who they claim.

---
<!-- _class: lead -->
# **Encoding vs. Encryption**
It's all about intention

---

<div class='container'>
<div class='col'>

# Encoding
- Not intended to remain secret
* that is, no **Confidentiality**
</div>

<div class='col'>

# Common Schemes
- ASCII
- UTF-8/16/32
- Braille
- Morse Code
- Base64
</div>

---

![bg right:42% 100%](images/Dolphin.jpeg)
# Example: Cetacean Cipher
- "Hello, Anti-Cast!" encoded:
* EEEEEEEEEeEEeEEEEEEEEEEEEeeEEeEeEEEEEEEEEeeEeeEEEEEEEEEEEeeEeeEEEEEEEEEEEeeEeeeeEEEEEEEEEEeEeeEE EEEEEEEEEeEEEEEeEEEEEEEEEeeEeeeEEEEEEEEEEeeeEeEEEEEEEEEEEeeEeEEeEEEEEEEEEEeEeeEeEEEEEEEEEeEEEEeeEEEEEEEEEeeEEEEeEEEEEEEEEeeeEEeeEEEEEEEEEeeeEeEEEEEEEEEEEEeEEEEe
<sub>Try it yourself: https://www.a.tools/Tool.php?Id=389</sub>
---

<div class='container'>
<div class='col'>

# Encryption
- Intended to remain secret
* Yes! **Confidentiality**
* Requires 1 or more "keys"
* Keys are just **really** big numbers
</div>

<div class='col'>

# Common Schemes
- Symmetric - 1 key
  - DES
  - AES
- Asymmetric - 2+ keys
  - RSA
  - ECC
</div>

---

![bg](images/Ciphertext.gif)

---
<!-- _class: lead -->
# **Symmetric Encryption**
Pretty much all cryptography before the 1970s

---

# Symmetric Encryption
<div class='container'>
<div class='col'>

## Pros
* Same key to encrypt/decrypt message
= Easy to understand
* Simple algorithms
= Very fast
</div>

<div class='col'>

## Cons
* Keys must be shared via a secure channel before communication
= Difficult!
* One key per communication group
= Key management becomes untenable
* Does not protect Integrity, ensure Non-repudiation, provide Authentication
= Limited Use
</div>

---
<!-- _class: lead -->
# **Example: ROT13**
Hello, Anti-Cast!
![w:125](images/SymmetricKey.png)
ROT13
Uryyb, Nagv-Pnfg!
ROT13
![w:125](images/SymmetricKey.png)
Hello, Anti-Cast!

---
<!-- _class: lead -->
# **Asymmetric Encryption**
The enabler of the modern internet

---

# Asymmetric Encryption
<div class='container'>
<div class='col'>

## Pros
* One **key pair** per identity
= Easy to manage
* Public keys can be shared over insecure channel
= Much easier than secure channel
* Provides Confidentiality, Integrity, Non-repudiation & Authentication
= Secure communications over insecure networks

</div>

<div class='col'>

## Cons
* Complicated algorithms
= Not fast
</div>

---

<!-- _class: lead -->
# **Example: ROT7 + ROT19**
Hello, Anti-Cast!
![w:125](images/PublicKey.png)
ROT7
Olssv, Huap-Jhza!
ROT19
![w:125](images/PrivateKey.png)
Hello, Anti-Cast!

--- 

<!-- _class: lead -->
# **Hash Functions**
Subheading TBD

---

# Hash Functions
<div class='container'>
<div class='col'>

- Maps any data to a (probably) unique fixed-length value
- Can't be easily reversed
- Ensures Integrity
* HELLOANTICAST
  - 8+5+12+12+15+1+14+
  20+9+3+1+19+20
  - Hash: 0139
</div>
<div class='col'>

| Letter | Number | Letter | Number |
|-|-|-|-|
| H | 8 | N | 14 |
| E | 5 | T | 20 |
| L | 12 | I | 9 |
| O | 15 | C | 3 |
| A | 1 | S | 19 |

<sub>Note: this is a terrible hash function. Do not use this for anything.
</div>

<!--
Max letter = 38
-->

---

<!-- _class: lead -->
# **Signing**
Subheading TBD

---

<!-- _class: lead -->
# **Certificates**
Subheading TBD

---

<!-- _class: lead -->
# **PKI**
Subheading TBD

---

<!-- _class: lead -->
# **Real-World Uses**
Subheading TBD

---

