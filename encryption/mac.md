# Message Authentication code

HMAC provides message integrity and authentication (the message hasn't been
altered, and we know who sent it).

    hash = hmac(ciphertext, key)
    send(hash + ciphertext)

    hash, ciphertext = parse(recieve())
    assert hmac(ciphertext, key) == hash

Hence, `key` is used as THE piece of identification. Only someone with that key
can practically (practically, because mathematically, there are some
collisions, but the probability of finding one is really small) produce the
same hash.

## Storage

We take the scenario where we want to build a password-protected storage.

The storage's content is encrypted, and then signed using hmac to protect
against padding oracle attacks.

To hmac sign, we need a hmac key. **The hmac needs to be secret.** This key
cannot be the password, because otherwise the user's identity would be bound to
his password (ie. he can't change it). So we need to generate a hmac key,
encrypt it using the password, then store it.

### Loading from the file

    password = getpassword()
    hmackey_enc = loadfromfile('hmackey')
    hmackey = decrypt(hmackey_enc, password)

    tag, content_enc = parse(loadfromfile('content-file'))
    assert tag == hmac(content_enc, hmackey)
    content = decrypt(content_enc, password)

Note that it is safe to do a `decrypt(hmackey_enc, password)` without any
preceding mac check because we don't need to protect ourselves from padding
oracle attacks, since we can generate the hmackey to be exactly the length of
the cipher block.

## References

- <http://www.crypto-it.net/eng/theory/mac.html>
- HMAC reference: <https://tools.ietf.org/html/rfc4868>

