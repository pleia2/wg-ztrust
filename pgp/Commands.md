# Commands

Here are some common PGP commands.
We are using `gpg` here as a PGP-workalike
because it is common on Unix systems and standard on Linux.

## Some GPG Commands

* for collecting keys from other people

    gpg  --allow-weak-key-signatures  --import  keyfile

* to share your public key with others

    gpg  --armor  --export  mykeyid  >  mykeyid.asc

* for signing keys of other people

    gpg  --default-cert-level 3  --sign-key  hiskeyid

You can then export keys of other people (now with your signature)
the same way as you export your own public key (above).

* for signing a file

    gpg  --armor  --detach-sign  file-to-sign

* for verifying a file

    gpg  --verify  signed-file.asc




gpg --full-generate-key
gpg --list-keys
gpg --list-secret-keys
gpg --export -a "your-email@example.com" > public_key.asc
gpg --detach-sign file.txt
gpg --verify file.txt.sig file.txt
gpg --armor --export YOUR_KEY_ID





gpg --full-generate-key

                          You will be prompted to select key type, key size, and expiration date. Once completed, your key pair will be generated.

    List all keys :

a.   List all public keys in your keyring:

gpg --list-keys

b.   List all secret (private) keys :

gpg --list-secret-keys

     Export keys (Public & Private) :

a.   To share your public key with others:

gpg --export -a "your-email@example.com" > public_key.asc

b.   Creating a backup of your private key in case of system failure:

             
gpg --export-secret-keys -a "your-email@example.com" > private_key.asc

    Encrypt and decrypt a file :

a.   Encrypt a file:

      
gpg --encrypt --recipient "recipient@example.com" file.txt

b.   Decrypt a file:

      
gpg --decrypt file.txt.gpg > file.txt

    Sign and verify a signed file :

                     a.   Sign a file:

                            
gpg --sign file.txt

b.    For a detached signature:

gpg --detach-sign file.txt

This creates file.txt.sig, which can be used to verify the integrity of file.txt.

c.    Verify signed file:

                            
gpg --verify file.txt.sig file.txt

                            If the signature is valid and the file has not been tampered with, GPG will confirm it.

Enhancing Repository Security with Signed Git Commits

Configure GitHub with your previously generated public GPG key and use it to sign commits on a server.

a.  Add your GPG key to GitHub :

                                         i.  Retrieve your public GPG key

                                              
gpg --armor --export YOUR_KEY_ID

b.    Copy the output and add it to GitHub :

                                         i.  Go to GitHub → Settings → SSH and GPG keys

                                         ii. Click New GPG key, paste the key, and save it

c.     Configure Git to use your GPG key on the server :

                                         i.  git config --global user.signingkey YOUR_KEY_ID

                                         ii. git config --global commit.gpgsign true

     This ensures all commits are signed by default

d.    Sign a commit and push :

                                         i. Create a signed commit

                                             git commit -S -m "Signed commit"

                                             git push origin main

e.     Verify the commit signature :

                                          i. git log --show-signature -1

     This confirms that your commit is correctly signed and verified on GitHub
     
     
     
     
