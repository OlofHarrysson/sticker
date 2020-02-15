---
title: Voice Recognition
description: Butler voice commands
published: true
date: 2020-02-15T20:35:54.944Z
tags: voice, speech, ai
---

# Using Butler

## Overview

Butler utilizes Final Cut Pro's xml support to transfer the details of your libraries, events, projects, and clips between Final Cut and third-party applications ([more info](https://support.apple.com/guide/final-cut-pro/use-xml-to-transfer-projects-verdbd66ae/mac)). The typical workflow to use Butler is therefor to send the xml from **Final Cut &rarr; Butler &rarr; Final Cut.**


## Voice Commands

Butler is built to recognize certain voice commands. Like other voice assistants, Butler starts paying attention to what you're saying when it hears a certain **wake word** - in this case **Butler**. The immediately following words are the **command words** which describes what you'd like Butler to do.

Butler~(BETA)~ starts of with two primary commands.
- **Butler add marker \*marker-name\*** adds a marker to the timeline of the clip. Note that the marker name should consist of a single word.
- **Butler start clip** and **Butler stop clip** starts/stops a virtual clip and adds the clip to a keyword collection.

> **Suggested use cases**
Add markers to easily find interesting moments in a long or repetetive video.
Add markers to categorize and search videos.
Start and stop clips to organize takes.
{.is-info}

Want more features? Tell us what  them to the [Feature Requests](../../html/featurerequests)

## Use Butler
#### Prepare Media for Butler
- Import the footage containing Butler commands into its own event in Final Cut
- Select the event and press <kbd>File</kbd> &rarr; <kbd>Export XML</kbd> from the Final Cut menu. Choose a name and save the file into the input_xml folder located in the butler project.

#### Enrich XML
- Navigate to the butler project in your terminal
- Run the command `python docker_enrich_xml.py --xml_file=input_xml/*my-xml-file*.fcpxml` but replace \*my-xml-file\* with the name of the file that was exported from Final Cut.

Thats it! The enriched xml file will, with the default settings, be imported to Final Cut and saved to the folder named output if one wishes to import it manually. 

To change the default settings, open the file `settings.py` in a text editor and change e.g. `self.send_to_finalcut = True` to `self.send_to_finalcut = False` if you don't want the enriched xml file to be automatically imported to Final Cut.
