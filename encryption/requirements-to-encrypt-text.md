# Text encryption requirements

The requirement trees of encryption systems.

# Encrypt fixed size text

Fixed size here means that the length of the text must be a multiple of the
length of the cipher's block size.

1. Cipher block
    1. fixed length key
        1. user password
        2. salt

# Encrypt arbitrary size text

1. Padded stream cipher
    1. HMAC
        1. fixed length key
            1. user password
            2. salt
    2. Cipher block
        1. fixed length key
            1. user password
            2. salt

You need to HMAC sign payloads to resist padding oracle attacks.
