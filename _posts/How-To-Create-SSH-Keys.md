---
# can edit: title, date, categories, and tags
layout: post
title: "SSH-Key Setup"
date: 2022-08-16 12:00:00 -0500
categories: [Homelab]
tags: [Homelab, Security, SSH]
---

## Encryption

There are different types of encryptions when it comes to SSH keys.
Those keys are:
- RSA 
- DSA 
- ECDSA 
- EDDSA 

<!-- TODO: This may change, so I will keep this in here 8/16/2022 -->
<!-- ### EDDSA
Very new, and favored by most modern cryptographic libraries.
Performance wise, they are actually the fastest algorithm across the spectrum. It provides the highest level of security when compared to key length. It also improves on the insecurities found in ECDSA, -->

## Choosing an Algorithm and Key Size
SSH supports several public key algorithms for authentication keys. These include:

### RSA
RSA is the most commonly used form of encryption. Larger keys do require more time to generate.
Specialized algorithms (Quadratic Sieve & General Number Field Seive exists to factor the integers).
A key size of at least 2048 bits is recommended for RSA; 4096 bits is better. RSA is getting old and significant advances are being made in factoring. Choosing a different algorithm may be advisable. It is quite possible the RSA algorithm will become practically breakable in the foreseeable future. All SSH clients support this algorithm.

### DSA
It has notoriety for security issues which makes it less popular. It has faster signature generation, but it is slow for validation. It also requires the use of randomly generated, unpredictable, and secure value that, if discovered, will reveal the private key.

### ECDSA
ECDSA is fairly new but not as popular as EDDSA.
Public keys are twitch the length of the desired bit security.
Vulnerable if the pseudo random number aren't cryptographically strong.
This is probably a good algorithm for current applications. Only three key sizes are supported: 256, 384, and 521 (sic!) bits. We would recommend always using it with 521 bits, since the keys are still small and probably more secure than the smaller keys (even though they should be safe as well). Most SSH clients now support this algorithm.

### ED25519 
This is a new algorithm added in OpenSSH. Support for it in clients is not yet universal. Thus its use in general purpose applications may not yet be advisable.

```bash
The algorithm is selected using the -t option and key size using the -b option. The following commands illustrate:

ssh-keygen -t rsa -b 4096
ssh-keygen -t dsa 
ssh-keygen -t ecdsa -b 521
ssh-keygen -t ed25519
```
## Generating SSH Keys (Github; ,could be used for others)

You do not need to open this in git bash but I highly recommend it. CMD could not work but I have not tried with that yet.

First you will want to generate an SSH-Key.
```bash
$ ssh-keygen -t ed25519 -C "your_email@example.com"
```
<br>

I recommend putting in your email address and not leaving the quotes there. E.x.: `ssh-keygen -t ed25519 -C johdoe@gmail.com`.
This will create a new SSH key, using the provided email as a label.
`Generating public/private algorithm key pair.`

<br>

When you are prompted to "Enter a file in which to save the key", press Enter. This will allow the file to end up in the default file location: `~/.ssh/`.

<br>

At the prompt, type a secure passphrase (you honestly do not need to type anything), and press 'Enter'. 

## Adding your SSH Key to the ssh-agent

Before adding a new SSH key to the ssh-agent to manage your keys, you should have checked for an existing SHH key and generated a new SSH key.

- Ensure the ssh-agent is running.

```bash
# start the ssh-agent in the background
$ eval "$(ssh-agent -s)"
> Agent pid <different number every time>
```

- Add your SSH private key to the ssh-agent

```bash
$ ssh-add ~/.ssh/id_ed25519
```

- Every time you have a problem with SSH keys, make sure to start up the SSH agent and also add the key back.

# New song to listen to:

Thank you for reading this small post, here is some music!
<br>
<iframe style="border-radius:12px" src="https://open.spotify.com/embed/track/1QbfsyV1NWJpHlJd0SsMPR?utm_source=generator" width="100%" height="80" frameBorder="0" allowfullscreen="" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture"></iframe>

<br>
<br>

_Revision 0.1 - 8/16/2022: Initial Upload_
<br>
