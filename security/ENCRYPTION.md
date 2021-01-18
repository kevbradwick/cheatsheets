# Encryption

Encrypt a directory usin OpenSSL (v1.1.1)

    tar -czf - [directory] | openssl enc -aes-256-cbc -md sha512 -pbkdf2 -iter 100000 -salt -out FILE.tar.gz

Bash function

    function encrypt_directory() {
        tar -czf - $1 | openssl enc -aes-256-cbc -md sha512 -pbkdf2 -iter 100000 -salt -out $1.enc.tar.gz
    }

Decrypt the file using OpenSSL

    openssl enc -d -aes-256-cbc -md sha512 -pbkdf2 -salt -iter 100000 -in FILE | tar xz -C .

Bash function

    function decrypt_directory() {
        openssl enc -d -aes-256-cbc -md sha512 -pbkdf2 -salt -iter 100000 -in $1 | tar xz -C .
    }