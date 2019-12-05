# SSH

## SSH fingerprint

The fingerprint is based on the public key. It is used to easily compare two
public keys

### Generate fingerprint

    $ ssh-keygen -lf ~/.ssh/id_rsa.pub

To get a visual representation of the key:

    $ ssh-keygen -lvf ~/.ssh/id_rsa.pub

## `.ssh/known_hosts`

This is used to make sure that we are connecting to the right host. When we
connect to an SSH server, we request it's public key (hence we get its
fingerprint), which we compare against the ones stored in `known_hosts`.

If it isn't known, there are two possible cases:

1. you never connected to that server before, and ssh can't guarantee it's
identity (common case).
2. The keys have changed. This is weird, and you should be extra careful (it
might be someone running a man-in-the-middle attack on you. If you type in your
password, they'll receive it in clear).

In both cases, you'll be given the option to add the key automatically to the
`known\_hosts`. Doing that will mean that you trust the server you're talking
to is the right one.

> So, what's good practice? (and please be easy to do)

You can go ahead an answer `yes` (add the to the `known_hosts`) file, but then
*make sure that the fingerprint of the server and the one in `known_hosts`
match*.


    $ ssh-keygen -lf ~/.ssh/known_hosts

Shows you all the finger prints you trust. Then find the server's ssh
fingerprint somewhere else (on the website, contact sysadmin), and compare
them.

This is especially important if you are in case (2). In fact, if it looks
especially weird, you might want to answer no and add the public key manually

### Ask server for it's public key

Note: asking the server for the public key this way, and then adding it to the
`known_hosts` files is just like connecting and then saying "yes, add to the
known\_host file". You should find *another* way to confirm the server's
public key if you want to add it to your `known_hosts` file

    $ ssh-keyscan -t rsa <host>

To get the server's fingerprint:

    $ ssh-keyscan -t rsa <host> | ssh-keygen -lf -

## File permissions

It makes sense for the `.ssh` folder to only be readable from the current user,
and no one else. Hence:

    $ chmod 700 ~/.ssh

Similarly, the private key should only be readable/writable by the current
user.

    $ chmod 600 ~/.ssh/id_rsa

`authorized_keys` is less obvious, but `ssh-import-id` seem to set it to 0600
as well

    $ chmod 600 ~/.ssh/authorized_keys

However, it makes sense for the public keys/known\_hosts to be readable by
anyone

    $ chmod 644 ~/.ssh/*.pub ~/.ssh/known_hosts

## Running an SSH server (`sshd`)

Configuration file: `/etc/sshd_config`

### Allow someone to connect to the server

Manually add their public key to `authorized_keys` file, or use a utility:

    ssh-import-id gh:math2001

This fetches my (math2001) public key from GitHub
(<https://github.com/math2001.keys>), and adds it to the current
`authorized_keys` on its own.

### What is my server's public key?

The server's public keys are stored by default here:

    /etc/ssh/ssh_host_rsa_key¬
    /etc/ssh/ssh_host_ecdsa_key¬
    /etc/ssh/ssh_host_ed25519_key

(You can change this in the config file)

### Disallow password authentication

It's a good idea, so that you require people to use a ssh key. Add this to the
config file:

    PasswordAuthentication no

