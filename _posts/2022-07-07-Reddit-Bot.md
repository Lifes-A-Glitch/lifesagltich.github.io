---
# can edit: title, date, categories, and tags
layout: post
title: "Reddit Bot: Scraping Subthreads"
date: 2022-07-04 20:00:00 -0500
categories: [Reddit-Bot]
tags: [Reddit, Bot]
--- 

# Details Details Details...

To explain why I am even talking about this is because one day I got miffed that I could not get an invite for something I wanted on a subreddit of Reddit. I wanted to know when someone was to make a post, and I could connect it via keywords. At that point in time, the bot would notify me via SMS. That _is_ the plan at least.
<br>
<br>
This bot was designed to scrape any subreddit someone designates. Searching for keywords in the titles, to searching for keywords in the descriptions.

## Packages Needed
_**Python 3.10.X was used for this project**_

Python Dotenv is used to store the bot's credentials.
    - `pip install python-dotenv`

PRAW is used to interact with the Reddit API.
    - `pip install praw`

__Incase anything goes wrong, uninstall all the libraries (including the ones not in this project) with: `pip freeze | xargs pip uninstall -y`__

## Description

The `python-dotenv` package is for the user to create their own `.env` file that allows for variables to be hidden when they push anything up to a repository. This is only if they have a `.gitignore` file that is custom or premade.
<br>

The `praw` is the Python Reddit API Wrapper package that allows the bot communicate with Reddit services/servers. More documentation about it can be explained here: [PRAW](https://praw.readthedocs.io/en/stable/getting_started/authentication.html#password-flow).

## The Code Itself (Work In Progress)

This is the structure to what you, as a reader, will want to base yours off of. I will be updating this slowly as I work on it. I would like to make it more customized and user friendly when it comes to CLI (Command Line Interface). 

### Notes
In the code provided below, there is a variable like `"{BOT-NAME-HERE}"`. The maker of the bot will need to replace that with their bot's name. Such as, `"Hendricks"`, as an example

```python 
import praw
import os
from dotenv import load_dotenv

# For .env file
load_dotenv()

USERNAME = os.getenv("REDDIT_USER")  # Reddit username
USER_PASSWORD = os.getenv("REDDIT_PASS")  # Reddit password
CLIENT_ID = os.getenv("REDDIT_CLIENT_ID")  # At least a 16 character long string found in the Reddit app
CLIENT_SECRET = os.getenv("REDDIT_CLIENT_SECRET")  # At least a 20 character long string found in the Reddit app


# Reddit connection
redditConnection = praw.Reddit(
    client_id=CLIENT_ID,
    client_secret=CLIENT_SECRET,
    user_agent="{BOT-NAME-HERE}",
    redirect_uri='http://localhost:8080',
    username=USERNAME,
    password=USER_PASSWORD,
)

# Prints the owner (user) of the bot
 print(redditConnection.user.me())

# Testing on the subreddit r/test
# This will ACTUALLY post to the r/test subreddit, go check the subreddit out for a post by your bot.
 redditConnection.subreddit("test").submit("Test of Reddit", url="https://reddit.com")

```
<br>

# New song to listen to:
<iframe style="border-radius:12px" src="https://open.spotify.com/embed/track/3XctWgpqES8k6NcpJuS1jA?utm_source=generator" width="100%" height="80" frameBorder="0" allowfullscreen="" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture"></iframe>

<br>
<br>

_Revision 0.1 - 7/4/2022: Initial Upload_
<br>

_Revision 1.0 - 7/4/2022: Correcting Grammar, and major change_

<br>