---
marp: true
transition: fade-out
theme: default
class: 
  - invert
paginate: false
backgroundColor: #000
style: |
  .container{
    display: flex;
  }
  .col{
    flex: 1;
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
</div>

<div class="col">

* Hashing Functions
* Signing
* Certificates
* PKI
</div>

---

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

![bg right](images/Shaggy.jpg)
# Non-Repudiation
### Ensures an author cannot refute authorship of a message.

---

![bg left:40% 110%](images/Popeye.jpg)
# Authentication
### Provides proof an author of a message is who they claim.

---

# **Encoding vs. Encryption**

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
* yes **Confidentiality**
</div>

<div class='col'>

# Common Schemes
- Symmetric
  - DES
  - AES
- Asymmetric
  - RSA
  - ECC
</div>

---

![bg](images/Ciphertext.gif)

---

# **Symmetric Encryption**

---


