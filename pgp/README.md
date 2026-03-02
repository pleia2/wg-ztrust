# ztrust/pgp

This is the ztrust/pgp folder with various PGP keys of members
of the z/OS and z/VM and z/Linux communities.

## Signing

PGP keys found here contain signatures which may extend into the larger
Web of Trust. In any case, signatures on these keys serve to assure
their ownership and veracity.

Cross-signed PGP keys inherently extend trust for themselves.
One purpose of this collection is to also sign PKI root certificates
found in the ztrust/pki folder.

## Naming

An example naming convention is ...

`0x` *key ID* (16 hex digits) `-` *email address* `-public.asc`

This makes them easy to find based on email address
but also allows them to be sorted by long form key ID.

Most keys here have a file type extension of `.asc`
indicating that they are ASCII-armored.

**Important note:** use the key ID (long hexadecimal form)
to refer to PGP keys because the email address is often imprecise.
A given email address can appear on *many* PGP keys
and a single PGP key pair can have *multiple* email addresses on it.
But the key ID is unique to each key.


