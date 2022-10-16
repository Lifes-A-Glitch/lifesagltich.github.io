---
# can edit: title, date, categories, and tags
layout: post
title: "SSH-Key Setup"
date: 2022-08-28 12:00:00 -0700
categories: [Homelab]
tags: [Homelab, Security, SSH]
---

# SSH-Key Setup Overview

With SSH keys, you can do so much more when it comes to security. SSH keys can be used in remote version control/file storage sites such as github, bitbucket, and gitlab (there are others out there as well). They can also be used to log into remote servers as well. There are many practical uses for SSH keys, but for now we are going to focus on generating the keys. On this page, I will also mention how to add the keys to the ssh-agent.

**Over time I will update this page to include setting up Github (and other repo services), as well as ssh'ing into remote servers.**

## Encryption
There are different types of encryptions when it comes to SSH keys.
Those keys are:
- RSA 
- DSA 
- ECDSA 
- EDDSA
- ED25519 

## Choosing an Algorithm and Key Size
SSH supports several public key algorithms for authentication keys. Listed below are the most common algorithms.

### RSA
RSA is the most commonly used form of encryption, but larger keys do require more time to generate.
RSA is considered a part of the specialized algorithms (Quadratic Sieve & General Number Field Seive exists to factor the integers).
A key size of at least 2048 bits is recommended for RSA; 4096 bits is better. RSA is getting old and significant advances are being made in factoring updates for it. Choosing a different algorithm may be advisable, and it is quite possible the RSA algorithm will become practically breakable in the foreseeable future. All SSH clients support this algorithm.

### DSA
It has notoriety for security issues which makes it less popular. It has faster signature generation, but it is slow for validation. It also requires the use of randomly generated, unpredictable, and secure value that, if discovered, will reveal the private key.

### ECDSA
ECDSA is fairly new but not as popular as EDDSA.
Public keys are twitch the length of the desired bit security.
Vulnerable if the pseudo random number aren't cryptographically strong.
This is probably a good algorithm for current applications. Only three key sizes are supported: 256, 384, and 521 (sic!) bits. We would recommend always using it with 521 bits, since the keys are still small and probably more secure than the smaller keys (even though they should be safe as well). Most SSH clients now support this algorithm.

### EDDSA
Very new, and favored by most modern cryptographic libraries.
Performance wise, they are actually the fastest algorithm across the spectrum. It provides the highest level of security when compared to key length. It also improves on the insecurities found in ECDSA. (I will not be showing the `ssh-keygen` command for it... _for now_)

### ED25519 
This is a new algorithm added in OpenSSH. Support for it in clients is not yet universal. Thus its use in general purpose applications may not yet be advisable.

## Command Examples
```bash
The algorithm is selected using the -t option and key size using the -b option. The following commands illustrate:

ssh-keygen -t rsa -b 4096
ssh-keygen -t dsa 
ssh-keygen -t ecdsa -b 521
ssh-keygen -t ed25519

tested
```
## Generating SSH Keys (Github, but could be used for others)

You do not need to open this in git bash but I highly recommend it. CMD could not work but I have not tried with that yet.


For this tutorial I will be using the ed25519 algorithm.
First you will want to generate an SSH-Key:
```bash
$ ssh-keygen -t ed25519 -C "your_email@example.com"
```
<br>

I recommend putting in your email address and not leaving the quotes there.  
* Ex: `ssh-keygen -t ed25519 -C johdoe@gmail.com`.

This will create a new SSH key, using the provided email as a label.
* What is shown: `Generating public/private algorithm key pair.`

<br>

When you are prompted to "Enter a file in which to save the key", press Enter. This will allow the file to end up in the default file location: `~/.ssh/`.

<br>

At the prompt, type a secure passphrase (you honestly do not need to type in a password if you do not want to), and press 'Enter'. 

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

## Notes:
- Every time you have a problem with SSH keys, make sure to start up the SSH agent and also add the key back.

- If you want to use the SSH key for other things (like logging into a server without password authentication), then you would use a command like `ssh-copy-id -i ~/.ssh/<what-ever-ssh-key-you-go-with> user@host` to copy the key to the server.

# New song to listen to:

Thank you for reading this small post, here is some music!
<br>
<iframe style="border-radius:12px" src="https://open.spotify.com/embed/track/1QbfsyV1NWJpHlJd0SsMPR?utm_source=generator" width="100%" height="80" frameBorder="0" allowfullscreen="" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture"></iframe>

<br>
<br>

_Revision 0.1 - 8/28/2022: Initial Upload_
<br>

_Revision 1.0 - 10/15/2022: Added another command_
<br>