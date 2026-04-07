# Code Signing

This page is a simple overview of code signing.
Details of specific code signing methods are discussed in per-method
files as the need arises. It is organized as follows:

* Code Signing Purpose - why we sign code
* Code Signing Trust Models - how we establish trust
* Code Signing Methods - how we create a signature

## Code Signing Purpose

We sign software packages ("deliverables" or "artifacts" or "packages")
to ensure intact and undisrupted delivery of the code. In the 21st
century there is [concern about the software supply chain](/Questions-Answers.md). (Indeed,
concern about *all* supply chains, though our focus is software.)

## Code Signing Trust Models

There are two popular "trust models" used for code signing:
* Public Key Infrastructure (PKI), using the same services as are used for web site certification
* Pretty Good Privacy (PGP), using classical peer-to-peer cryptographic trust

**In the PKI model**, the signator must acquire a **code signing certificate**
from the Certificate Authority (CA) of choice.  Digital certificates have different uses
and purposes, so it is important to validate that the certificate used to sign the code
was intended for code signing. A chain of trust is established by the Certificate Authority
maintaining control and ultimate authority over their endorsement of these secondary
(or in some cases, tertiary or quaternary...) certificates.

**In the PGP model**, the signator must create a key pair and should then
have the public half signed by other entities in the PGP space.  So rather than a single
root of trust maintained by a Certificate Authority, trust is established more communally,
and maintained in certain PGP servers as a record of trust.

In either case, the content to be delivered is first hashed (establishing integrity).
Then the key (the private key associated with the PKI cert, or the private half of the PGP pair) 
is used to encrypt the signature hash. Upon verification, the signature is decrypted using the
public key (or public half of the pair). If the decrypted hash matches an immediate re-hash of the
binary, then the content is confirmed as verified.

## Code Signing Methods

There are two primary mechanical methods of associating a signature with a piece of code:
* internal or embedded
* external or detached

In each case, a signature is derived which can then be used
to cryptographically ensure the content.

With an external or "detached" signature the payload remains completely unchanged. 
The file comprising the deliverable is hashed, a signature is created via encryption (per above), 
and that signature is stored as a separate and distinct file.

With an internal or "embedded" signature, the payload and signature are held together in one file.
The payload might be taken from an original separate file or it might have pre-defined structure for 
holding signatures.  Verification processes for such files must understand how much of this sort of
file must be re-hashed -- hashing a file with the attached signature will inevitably create a 
hashing mismatch when compared to the original (unsigned) file.


