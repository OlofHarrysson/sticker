---
title: Voice Recognition
description: Butler voice commands
published: true
date: 2020-04-04T14:40:26.956Z
tags: voice, speech, ai
---

# Using Butler

## Overview

Butler utilizes **Final Cut Pro**'s xml support to transfer the details of your libraries, events, projects and clips between Final Cut and third-party applications ([more info](https://support.apple.com/guide/final-cut-pro/use-xml-to-transfer-projects-verdbd66ae/mac)). The typical workflow to use Butler is therefore to send the xml from **Final Cut &rarr; Butler &rarr; Final Cut.**


## Voice Commands

Butler is built to recognize certain voice commands. Like other voice assistants, Butler starts paying attention to what you're saying when it hears a certain **wake word** - in this case **Butler**. The immediately following words are the **command words** which describe what you'd like Butler to do.

Butler~(BETA)~ starts of with two primary commands.
- **_Butler add marker \*marker-name\*_** adds a marker to the timeline of the clip. Note that the marker name should consist of a **single word** and can be **chosen freely** within the english language.
- **_Butler start clip_** and **_Butler stop clip_** starts/stops a virtual clip and adds the clip to a keyword collection.

> **Suggested Use Cases**
*Add markers to easily find interesting moments in a long or repetetive video.*
*Add markers to categorize and search videos.*
*Start and stop clips to organize takes.*
{.is-info}

Want more features? Tell us about them at the [Feature Requests](../../html/featurerequests) page

## Use Butler
<div style="background-color:lightblue;margin:0;padding:0;height:70vh;overflow:hidden;">
  <iframe id="inlineFrameExample"
  title="Inline Frame Example"
  width="100vh"
  height="100%"
  frameborder="0"
  style="overflow:hidden;height:100%;width:100%"
  allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
  allowfullscreen
  src="https://www.youtube.com/embed/Gk-wNunhERk">
  </iframe>
</div>

#### Prepare Media for Butler
- Import the footage containing Butler commands into its own event in Final Cut.
- Select the event and press <kbd>File</kbd> &rarr; <kbd>Export XML</kbd> from the Final Cut menu. Choose a name and save the file into the input_xml folder located in the butler project.


#### Enrich XML
- Navigate to the butler project in your terminal
- Run the command `python docker_enrich_xml.py --xml_file=input_xml/*my-xml-file*.fcpxml` but replace \*my-xml-file\* with the name of the file that was exported from Final Cut.
- Butler produces a new xml-file in the output folder of the project that contains the voice command information. Drag the file to Final Cut to import it.


To change the default settings, open the file `settings.py` in a text editor and change e.g. `self.send_to_finalcut = True` to `self.send_to_finalcut = False` to disable the enriched xml file to be automatically imported to Final Cut.
