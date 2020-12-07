Retrieve certificate information from host

    openssl s_client -connect duckduckgo.com:443 </dev/null

To print the certificates in the chain from host

    openssl s_client -showcerts -connect duckduckgo.com:443 </dev/null

Get just the certificate, pipe through

    sed -ne '/-BEGIN-/,/-END-/p'

Print certificate information from file:

    openssl x509 -text cert.pem  # entire things
    openssl x509 -issuer -subject -dates -noout cert.pem  # filter out

Use custom trusted certificate:

    openssl s_client -CAfile cert.pem -CApath /etc/ssl/certs \
        -connect hostname:port </dev/null

The server should give the entire cert chain (including the root?) to the client.
Things like openssl and curl expect this behaviour. Browser try to be smart and
combine caches and Authority Information Access to build the chain themselves if
broken. See
https://security.stackexchange.com/questions/64415/how-are-browsers-able-to-find-and-construct-an-alternate-trusted-chain-path

