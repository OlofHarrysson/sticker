---
title: Voice Recognition
description: Butler voice commands
published: true
date: 2020-02-13T12:41:58.973Z
tags: voice, speech, ai
---

# Using Butler

## Overview

Butler utilizes Final Cut Pro's feature to transfer the details of your libraries, events, projects, and clips between Final Cut Pro and third-party applications ([more info](https://support.apple.com/guide/final-cut-pro/use-xml-to-transfer-projects-verdbd66ae/mac)). The typical workflow to use Butler is therefore **Final Cut &rarr; Butler &rarr; Final Cut.**


## Voice Commands

Butler is built to recognize certain voice commands. Like other voice assistants, Butler starts paying attention to what you're saying when it hears a certain **wake word** - in this case **Butler**. The immediately following words are the **command words** which describes what you'd like Butler to do.

Butler~(BETA)~ starts of with two primary commands.
- **Butler add marker \*marker-name\*** adds a marker to the timeline of the clip. Note that the marker name should consist of a single word.
- **Butler start clip** and **Butler stop clip** Starts/stops a virtual clip and adds the clip to a keyword collection.

> **Suggested use cases**
Add a marker to easily find interesting moments in a long or repetetive video.
Add markers to categorize and search videos.
Start and stop clips to organize takes.
{.is-info}

Prepare Media for Butler
- Import the footage containing Butler commands into its own event in Final Cut

- Record video footage containing Butler voice commands
- Import the footage into Final Cut
- Export the footage as an XML file from Final Cut
- Create an enriched XML file with Butler
- Import the enriched XML file to Final Cut

To use Butler you'd have to follow the 

command words
export xml
run program
import xml
search xml
change xml
