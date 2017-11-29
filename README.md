# openssl-decrypt:<br>decrypt a file using our best settings

Syntax:

    openssl-decrypt <input file path> [output file path]
    
Example:

    $ openssl-decrypt example.txt.aes

Output is a new decrypted file:

    example.txt


## Settings

  * Symmetric encryption, i.e. we use the same password for encryption and decryption.
    We choose this because our users can understand symmetric more easily than asymmetic.

  * Encryption using the aes-256-cbc cipher algorithm.
    We choose this because it's a good balance of strong, fast, and portable.

  * Message digest using SHA-256.
    We choose this because it's the current default of the current openssl tool,
    and we set it explicity because openssl versions have different defaults.

  * Salt that is randomly generated.

  * The output file path defaults to the input file path without the suffix ".aes".


## Command

The command is:

    openssl aes-256-cbc -d -salt -md sha256
      -in "example.txt.aes"
      -out "example.txt"


## See also

These commands are similar:

  * [`gpg-encrypt`](https://github.com/SixArm/gpg-encrypt): 
    use GPG to encrypt a file using our best settings.
  
  * [`gpg-decrypt`](https://github.com/SixArm/gpg-decrypt): 
    use GPG to decrypt a file using our best settings.

  * [`openssl-encrypt`](https://github.com/SixArm/openssl-encrypt): 
    use OpenSLL to encrypt a file using our best settings.
  
  * [`openssl-decrypt`](https://github.com/SixArm/openssl-decrypt): 
    use OpenSSL to decrypt a file using our best settings.


## Tracking

  * Command: openssl-decrypt
  * Version: 2.0.0
  * Created: 2017-09-14
  * Updated: 2017-11-27
  * License: GPL
  * Contact: Joel Parker Henderson (joel@joelparkerhenderson.com)
