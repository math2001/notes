# Block ciphers

## Block cipher modes of operations

The problem is that an attacker can retrieve a lot of information without even
breaking the cipher if two identical plain texts are transformed into identical
cipher text. Hence, there are different strategies, *modes of operations* that
can be employed.

## `ECB` Electronic Codebook mode

Each block is encrypted independently, hence it is subject to the problem
described above.

## `CBC` Cipher-block chaining mode

To encrypt a cipher block, you XOR add the previous cipher block with the
current plain text block. Hence, each block depends on the previous, and two
identical text blocks will result in two different cipher blocks.

## Padding

<https://tools.ietf.org/html/rfc5246#section-6.2.3.2>
