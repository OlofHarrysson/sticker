---
title: Installation
description: 
published: true
date: 2020-01-28T18:30:27.529Z
tags: installation
---


# Installation

This guide will help you install Butler and verify that it was installed correctly.

> Before starting the installation, make sure that you meet the [requirements](TODO).
{.is-info}

## Docker
The easiest way to run Butler is through Docker. You can install Docker Desktop for Mac at [their website](https://www.docker.com/get-started). See [Advanced Installation](TODO) if you wish to install the program differently.

## Project Setup
> Not a developer? The [installation video](TODO) might help 
{.is-warning}

###### Clone the git repo
`git clone https://github.com/OlofHarrysson/editing-butler.git`
`cd editing-butler`

###### Build docker image
`python setup/build_docker.py`

## Test the Program
`python docker_enrich_xml.py`

###### Export a Final Cut XML-file
Move this to usage
1. Open Final Cut pro.
2. Select the event you wish to export.
> It's recommended that you create a new event. Make sure that the event contain videos with speech commands. Videos can be up to 15 minutes long ~(BETA)~.
{.is-warning}
3. Press to the top menu <kbd>File</kbd> ARROW <kbd>Export XML</kbd> and save the file in the input_xml folder located in the sticker project.

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



<p>Install Docker which will run the program. You can install Docker Desktop for Mac through [their website](https://www.docker.com/get-started).</p>

