# Encryption

Encrypt a directory usin OpenSSL

    tar -czf - [directory] | openssl enc -e -aes256 -out output.tar.gz

Bash function

    function encrypt_directory() {
        tar -czf - $1 | openssl enc -e -aes256 -out $1.enc.tar.gz
    }

Decrypt the file using OpenSSL

    openssl enc -d -aes256 -in $1 | tar xz -C .

Bash function

    function decrypt_directory() {
        openssl enc -d -aes256 -in $1 | tar xz -C .
    }