# ZTRUST Working Group

The ZTRUST working group exists to educate and inform members of
the System Z (mainframe) community about cryptographic trust issues,
starting with code signing.

The working group also exists to provide a "trust anchor" for the
System Z community which can be used for verifying delivered code
("artifacts") and related content.

One of the first questions people ask is, "How do I create a PGP key pair?".
<br/>
For that, see the [How-To](How-To.md) guide.

## Goals

1. Education/Information

As of this writing, many members of the Z community remain unfamiliar
with trust anchors, cryptographic signing, PKI and PGP, and related
topics. This working group will fill the gaps.

2. Trust Anchor

While many trust anchors, trust paths, and trust chains already exist,
it seemed helpful to establish a community trust anchor for those
software deliverables and related services which fall outside of
established and commercial trust space.

<!-- The TAC member sponsor of this working group is _TAC sponsor name_ -->

## Deliverables

1. documentation

2. PKI root certificates

3. PGP public keys

## Communication

This WG communicates on the following channels:

- mailing list being created by Tom Slanda (LF program coordinator)
- _no slack channel_ (but perhaps a Discord subchannel?)
- _presently all person-to-person email_

## Meetings

This WG presently meets on Mondays from 10AM til 11AM Eastern.
The meeting is hosted by Google Meet.

https://meet.google.com/aso-voon-sia

Also see the [Open Mainframe Project public calendar](https://calendar.openmainframeproject.org).

## Meeting notes

Meeting notes, recordings, and any presentations made during WG meetings
are available [here](meetings).

## Back Story

In the late 1980s, we got asymmetric cryptography.
The logic had been developed a decade earlier (two independent teams)
but it took some time for the idea to catch on. Originally seen as
a way to send very private messages, asymmetric crypto also gives us
is the ability to form *cryptographic* trust relationships, where we
can use digital media to assure authenticity.

At this time, there are three popular services which use asymmetric
crypto: PKI (SSL/TLS), SSH Secure Shell, and PGP "Pretty Good Privacy".
PKI and PGP support cryptographic trust for such things as code signing
and that is the focus of this effort.

## PGP keys

The `pgp` sub-directory has a number of PGP keys
contributed by members of the community. It forms a web-of-trust
because most of these PGP keys are cross-signed.

The signifcance of PGP is that it is person-to-person.
It goes deeper than commercial or institutional trust.
But establishing and maintaining personal trust can be time consuming.

## PKI certificates

The `pki` sub-directory has a number of PKI root certificates
contributed by members of the community. Some of these are signed
using PGP.

Most readers will understand that PKI is the differentiator between
`http` and `https` on the web. The latter is secured via SSL (now known
as TLS). Web servers speaking HTTPS must have a server certificate.
Technically, that certificate is a "PKI server certificate".

Ordinarily, PKI certificates are issued by a Certificate Authority (CA).
There are cases where a CA is not available or where an in-house
or home-grown CA is preferred. Root certificates found here are
of that sort. When they are signed using PGP, consumers have assurance
which they would not otherwise have.

## Rationale

*It's all about trust!*

Cryptography is easy. Key management is hard.

The keys are not significant. The *trust* is what matters.


