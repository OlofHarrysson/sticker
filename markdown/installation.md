---
title: Installation
description: 
published: true
date: 2020-01-28T19:31:52.117Z
tags: installation
---


# Installation

This guide will help you install Butler and verify that it was installed correctly.

> Before starting the installation, make sure that you meet the [requirements](TODO).
{.is-info}

## Easy Installation - Docker
The easiest way to run Butler is through Docker. You can get [Docker Desktop](https://www.docker.com/get-started) for Mac at their website. See [Advanced Installation](TODO) if you wish to install the program differently.

### Project Setup
> Not a developer? The [installation video](TODO) might help 
{.is-warning}

###### Clone the git repo
```bash
git clone https://github.com/OlofHarrysson/editing-butler.git
cd editing-butler
```
###### Build docker image
```python
python setup/build_docker.py
```

###### Test the Program
```python
python docker_enrich_xml.py --test
```

---

## Custom Installation
You can also run Butler without Docker. For this you need to install ffmpeg and Python 3.7+ on your system.

We would then recommended installing thought [Anaconda](https://www.anaconda.com/).





# Installation
## Setup a Google Cloud Project
1. Go to [https://cloud.google.com/](https://cloud.google.com/) and create an account.
2. Create a new project.

### Setup Google Cloud Storage
1. Go to [https://console.cloud.google.com/storage/](https://console.cloud.google.com/storage/)
2. Create a new bucket and remember the name. Use the default settings for the options.

### Enable the Speech to Text API
1. Go to the [https://console.cloud.google.com/apis/library/speech.googleapis.com](https://console.cloud.google.com/apis/library/speech.googleapis.com).
2. Press <kbd>Enable</kbd> and wait for the console page to load.
3. Go to the [Credentials](https://console.cloud.google.com/apis/credentials) page and press <kbd>Create credentials</kbd> -> <kbd>Service account key</kbd>.