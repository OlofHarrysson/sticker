---
title: Installation
description: 
published: true
date: 2020-01-19T17:38:30.511Z
tags: installation
---

# Outline
This guide will help you install Sticker and try it out on an example. There are two installation guides, one geared towards developers and one for

arrows
&#8593;
&#8592;
&#8594;
&#8595;

# Installation
## Install Docker
Docker allows for easy installation. You can install Docker Desktop for Mac through [their website](https://www.docker.com/get-started).

## Setup Splitter
1. Open a Finder window and navigate to the folder where you want to install the project.
2. Right click the folder and select New Terminal at Folder. A new window will open.
3. Copy the command into the terminal window and press enter <kbd>git clone https://github.com/OlofHarrysson/splitter.git</kbd>


## Setup a Google Cloud Project
1. Go to [https://cloud.google.com/](https://cloud.google.com/) and create an account.
2. Create a new project.

### Setup Google Cloud Storage
1. Go to [https://console.cloud.google.com/storage/](https://console.cloud.google.com/storage/)
2. Create a new bucket and remember the name. Use the default settings for the options.

### Enable the Speech to Text API
1. Go to [https://console.cloud.google.com/apis/library/speech.googleapis.com](https://console.cloud.google.com/apis/library/speech.googleapis.com).
2. Press <kbd>Enable</kbd> and wait for the console page to load.
3. Go to the [Credentials](https://console.cloud.google.com/apis/credentials) page and press <kbd>Create credentials</kbd>&#8594;<kbd>Service account key</kbd>.
4. Select "New service account" from the "Service Account" drop down. Give the new service account a name and give it the role of Project&#8594;Owner 
5. Press <kbd>Create</kbd> to download the file. Name the file google-key.
6. Move the downloaded file to the Splitter folder.




<p></p>

