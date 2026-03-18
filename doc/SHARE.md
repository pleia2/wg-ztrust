# SHARE

This document discusses in-person PGP key exchange
at conferences such as SHARE.

SHARE provides an excellent opportunity to establish trust,
including cryptographic trust, with peers in the Z community.

Be prepared to exchange key fingerprints as you encounter others
who need to connect with the web of trust.

## In Person

Face to face human interaction is the most sure way to form trust.
If the other person is not someone you know well, ask for a photograph
on a government-issued credential (driving license, passport, etc).
For purposes of establishing cryptographic trust, *this is not discourteous*.

The recommended method is simple:
Carry a business card or other printed report of your PGP "fingerprint".
When you meet a colleague who could benefit from cryptographic trust,
or who could help you in the same vein, give them the paper or card.

After meeting in person, acquire the *electronic* copy of the other
party's public key, import it to your own keyring, confirm carefully
that the fingerprint matches what you received, and then "sign" their key:

    gpg --sign-key *theirkeyid*

Then extract their key (now signed by you) and return it to them.

If you are confident about the identity of the other person,
you should apply a higher trust level:

    gpg --default-cert-level 3 --sign-key *theirkeyid*

(and then [re]extract)

## On Paper

It is ironic that we would use such low tech methods as paper
in the 21st century. But it makes sense.

Content printed on paper or similar durable physical media
is highly resistant to undetected tampering. By contrast, even the most
well-protected electronic media (example, portable flash drive) could be
modified by a malicious actor.


