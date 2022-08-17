<!-- ---
# can edit: title, date, categories, and tags
layout: post
title: "SSH-Key Setup"
date: 2022-08-16 12:00:00 -0500
categories: [Homelab]
tags: [Homelab, Security, SSH]
--- -->

## Generating SSH Keys

You do not need to open this in gitbash but I highly recommend it. CMD could not work but I have not tried with that yet.

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
<br>

_Revision 0.1 - 8/16/2022: Initial Upload_
<br>
