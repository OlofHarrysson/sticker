---
title: Installing Butler
description: 
published: true
date: 2020-02-22T17:36:17.198Z
tags: installation, google cloud, docker, test, install, installing
---

# Installation

This guide will help you install Butler and verify that it was installed correctly.

> Before starting the installation, make sure that you meet the [requirements](../markdown/requirements).
{.is-info}

> Not a developer? The [installation video](TODO) might help 
{.is-info}

## Easy Installation - Docker
The easiest way to run Butler is through Docker, a program that makes it easy to share code projects with others. You can get [Docker Desktop](https://www.docker.com/get-started) for Mac at their website. See **Custom Installation** below if you wish to install the program differently.

### After installing Docker
###### Clone the git repo
```bash
git clone https://github.com/OlofHarrysson/editing-butler.git
cd editing-butler
```

###### Build docker image
```python
python setup/build_docker.py
```

###### Test the program
```python
python docker_enrich_xml.py --xml_file=assets/setup_test.fcpxml --test_install==True
```

---

## Custom Installation
You can also run Butler without Docker. If you'd like to do this, we reccomend installing Butler thought [Anaconda](https://www.anaconda.com/). Other installation methods are not covered in this guide.

###### Clone the git repo
```bash
git clone https://github.com/OlofHarrysson/editing-butler.git
cd editing-butler
```

###### Create virtual environment
```bash
conda create -n butler_env python=3.7
conda activate butler_env
conda install -c conda-forge ffmpeg
pip install -r setup/requirements.txt
```


# Private Google Cloud Project
Butler~(BETA)~ runs on the **Google Cloud API SpeechToText**. Since this is costly to run for us (about $4/hour of speech), we suspend the program once the **daily limit** of requests is reached. This quota is not individual but **shared amongst all users**.

If you'd like to continue to use Butler after the daily limit is reached you'll have to create your own Google Cloud project.

### Setup a Google Cloud Project
1. Go to [https://cloud.google.com/](https://cloud.google.com/) and create an account.
2. Create a new project.

### Setup Google Cloud Storage
Googles SpeechToText service requires the sound file to be uploaded to Google's cloud storage.
1. Go to [https://console.cloud.google.com/storage/](https://console.cloud.google.com/storage/)
2. Create a new bucket and remember the name. Use the default settings for the options.

### Enable the Speech to Text API
1. Go to [https://console.cloud.google.com/apis/library/speech.googleapis.com](https://console.cloud.google.com/apis/library/speech.googleapis.com).
2. Press <kbd>Enable</kbd> and wait for the console page to load.
3. Go to the [Credentials](https://console.cloud.google.com/apis/credentials) page and press <kbd>Create credentials</kbd> &rarr; <kbd>Service account key</kbd>.
4. Set the role to Project Owner and create a json key. Don't share this key-file as anyone who gets a hold of it can access and use your Google Cloud project.
5. Move the file to the editing-butler directory.
6. Open the file `config.py` file in a text editor and change the google_key value to your file path. e.g. `self.google_key = myfilename.json`.
7. Test the program as described in the installation guide.