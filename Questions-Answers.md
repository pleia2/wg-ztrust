# Questions and Answers

Here are some common questions and some hopefully helpful answers.

* Q:
Should customers be getting signed artifacts only?

* A:
It depends.
In the 21st century, there is increasing concern over supply chain.
In the software industry, that is specifically concern over the
(no surprise here) *software* supply chain. With respect to code signing,
regulators, administrators, and executives require assurance that the
software artifacts have not been tampered with.

The real answer to the question depends on the risks.
Any software which might impact production work or operations
must be trustworthy. Signed software extends the chain of trust
from the vendor to the user/consumer. Code signing is an increasingly
important means of conveying trust. In absence of a signature,
the software *must* come by way of a trustworthy channel.

* Q:
What should I do with this PGP public key that I have generated?

* A:
First, get at least one other community member to sign it. <br/>
After that, use your key pair to cryptographically sign files as needed.

You can also use PGP encryption for email.
In that case, people will use your public key to encrypt a message
and you would decrypt it (having your secret key) when you receive it.
Email is not a focus of the ZTRUST effort, but is a fact of life
and PGP robustly protects (and authenticates) your email.

* Q:
What is the "fingerprint" of a PGP key and what is it used for?

* A:
All asymmetric key pairs have a fingerprint which reliably identifies them.

A PGP key fingerprint is commonly 40 hex digits in length.
It can be shown using a command like ...

    gpg --fingerprint keyid

 ... where *keyid* is some other identifier of the key pair.

Key pairs are usually tagged using a shorter hexadecimal string,
the last 16 digits of the full fingerprint. PGP keys can sometimes
also be tagged using the email address associated with the pair.
(But email addresses often get re-used and are therefore
less effective as an identifier.)

A PGP key fingerprint is often used in verifying a key.
The fingerprint can be printed on immutable or tamper-evident media (e.g., paper)
and shared with others in person.

* Q:
How do we "manage" keys?

* A:
It has been well said: <br/>
Crypto is easy. Key management is hard.

PGP keys are usually well managed using tools like `gpg`.
These implementations have a database of some sort underpinning them.

Learn to use the 16-hex-digit "key ID" for your PGP keys.

PKI certificates are best handled using unique common names.
If the common name is not unique, then the distinguished name *must* be unique.
If neither is unique, then the only recorse for managing "near" certificates
is the key fingerprints, and that leads to excess manual intervention.

Ensure that common names on PKI certificates are unique.
The common name forms part of the distinguished name, so if the common name
is unique then the distinguished name will be too.

* Q:
What is code signing?

* A:
Code signing is a method to confirm that code or other
digital binaries have not been altered. This method
leverages the Public Key Infrastructure (PKI) framework
to attests to the integrity of the code or binaries. Code
signing acts like a digital shrink wrap: the process
of code signing creates a "package" with the signed
code or file, if the "packaging" was not damaged when
received, then the file has not been tampered with and
can be trusted. And vice-versa: if the "packaging" was
damaged then the file has been tampered with and
cannot be trusted.

* Q:
Why is code signing important?

* A:
Code signing minimizes the risks of code tampering.
With signed code, the recipient gets a security warning
when the integrity check fails during download. This
helps recipients to avoid downloading tampered code
which may contain malware.

* Q:
What types of files can be signed?

* A:
You can sign all types of digital binaries including
drivers, firmware, containers, applications, mobile apps
as well as source code artifacts.


