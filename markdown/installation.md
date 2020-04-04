---
title: Installation
description: Pick your preferred method
published: true
date: 2020-04-04T14:49:21.360Z
tags: installation, google cloud, docker, test, install, installing
---


This guide will help you install Butler and verify that it was installed correctly.

> Not a developer? The [installation video](https://www.youtube.com/watch?v=RjP0nwNdP80) might help 
Before starting the installation, make sure that you meet the [requirements](https://www.editingbutler.com/markdown/requirements).
{.is-info}

## Easy Installation - Docker
The easiest way to run Butler is through Docker, a program that makes it easy to share code projects with others. You can get [Docker Desktop](https://www.docker.com/get-started) for Mac at their website. See **Custom Installation** below if you wish to install the program differently.

###### Install and Verify Docker
Download Docker and install it like any other Mac application. After installation, open the Docker app. It will need your admin password the first time. More information can be found at the [Docker website](https://docs.docker.com/docker-for-mac/install/). 	


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
> Creating a private google cloud project is **optional**
{.is-info}


Butler~(BETA)~ runs on the **Google Cloud API SpeechToText**. Since this is costly to run for us (about $4/hour of speech), we suspend the program once the **daily limit** of requests is reached. This quota is not individual but **shared amongst all users**.

If you'd like to continue to use Butler after the daily limit is reached you'll have to create your own Google Cloud project.

### Setup a Google Cloud Project
1. Go to [https://cloud.google.com/](https://cloud.google.com/) and create an account. Google offers [Free Credits](https://cloud.google.com/free/docs/gcp-free-tier) for new users.
2. Create a new project.

### Setup Google Cloud Storage
Googles **SpeechToText** service requires the sound file to be uploaded to Google's cloud storage.
1. Go to [https://console.cloud.google.com/storage/](https://console.cloud.google.com/storage/)
2. Create a new bucket and **remember the name**. Use the default settings for the options.

### Enable the Speech to Text API
1. Go to [https://console.cloud.google.com/apis/library/speech.googleapis.com](https://console.cloud.google.com/apis/library/speech.googleapis.com).
2. Press <kbd>Enable</kbd> and wait for the console page to load.
3. Go to the [Credentials](https://console.cloud.google.com/apis/credentials) page and press <kbd>Create credentials</kbd> &rarr; <kbd>Service account</kbd>. Give the service account a name, id and description of your choice and press <kbd>Create</kbd>.
4. Set the role to **Project Owner** and press <kbd>Continue</kbd>.
5. Press <kbd>Create key</kbd> to download the json-file that contains the key. Name it e.g. **mybutlerkey.json**. Don't share this key-file as anyone who gets a hold of it can access and use your Google Cloud project.
6. Press <kbd>Done</kbd> to complete the service account setup.
5. Move the file to the editing-butler directory.
6. Open the file `settings.py` file in a text editor and change the google_key value to your file name. e.g. `self.google_key = 'mybutlerkey.json'` and `self.google_bucket_name = 'mybucketname'` where mybucketname is the name of the bucket you chose earlier.
7. Test the program as described in the installation guide.