This folder holds PGP keys in "armored" format specifically for email use.
Keys found here which are used for other purposes, such as for signing,
may be found elsewhere but will be named differently elsewhere even though
the keyid remains the same.

The recommended filename format is ...

keyid `-` identity `-email.asc`

The keyid should be the long form, 16 hex digits prepended with `0x`.
									.
All keys in this project are public. The `-email.asc` suffix makes clear
that these keys are intended for encrypting email to the named recipient
(and that they are in armored format).


