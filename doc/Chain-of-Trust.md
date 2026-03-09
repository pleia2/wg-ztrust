# Chain of Trust

How do we explain the chain of trust? <br/>
It might help to relate it to the Chain of custody
in law enforcement.

## Chain of Custody

There is a useful Wikipedia article discussing the legal
"Chain of Custody". In short, when material essential to evidence
is handled, the handlers need to be identified. When the item is
eventually needed in court, all handlers must be known with assurance.

The Chain of Custody is a clear example of provenance.

## Chain of Trust

A chain of trust is similar, except that cryptographic trust
itself represents the assurance. One signator (or signatory)
conveys "trust" by cryptographically signing the key or identity
of another. If you trust ...

## ZTRUST and Chaining

When you acquire and use a web browser, the authenticity of any
target web site is verified using a PKI certificate. Your browser
trusts that PKI server certificate because the server certificate
chains back to a root certificate in your browser's trust store.
But how do you know that the specific root certificate (or any of
the certificates in your browser's trust store) is itself authentic?

The trust store delivered with a web browser is pre-packaged
for convenience in a consumer context. Other chains of trust require
more robust verification. The PKI bundle in the ZTRUST project includes
cryptographic signatures which can chain back to one or more certificates
or keys which you can verify in person with trusted individuals.

https://en.wikipedia.org/wiki/Chain_of_custody

https://en.wikipedia.org/wiki/Chain_of_trust

https://www.thefreedictionary.com/provenance


