---
sidebar_label: 'Setup a Moose Assistant'
sidebar_position: 4
---

import ReactPlayer from 'react-player'  
import MooseAIAssistantDemonstration1 from '../../static/Demos/MooseAIAssistantDemonstration1.mp4'

# Overview
Moose AI is an AI smart assistant widget that can be added to a SEMOSS insight to assist the user with data inquiries. You can follow the steps below to set up Moose AI on your CFG instance. 

<ReactPlayer controls url={MooseAIAssistantDemonstration1}/>

# Setup a Moose Assistant

**Stop any running instance of SEMOSS on your machine**
- Open your browser and close all tabs that SEMOSS open.
- Go to Eclipse and stop your Tomcat server.

**Update SEMOSS**
- In File Explorer, go to your **Workspace** folder.
- Select both **Semoss_Dev** and **Monolith_Dev** folders, right-click, and click “**SVN Update**”.
- Go to the **SemossWebAPPUI** folder, right-click, and then click “**SVN Update**".

![SVNUpdate](../../static/img/MooseAI/SVNUpdate.png)

- Open Eclipse > Project Explorer, go to **Semoss_Dev** and **Monolith_Dev**, right-click and click “**Refresh**”.
- Click on **Project** tab at the top, then click on “**Clean**”.  

**Update RDF Map**
- Inside **Eclipse**, click anywhere and open the **Resource Prompt** using `Control+Shift+R`.
- Search for **RDF_Map** and click to open.

![RDF Map](../../static/img/MooseAI/RDFMap.png)

- Add or replace the following lines to the end of the RDF Map file:
    `SQL_MOOSE_MODEL alpaca`
    `MOOSE_MODEL guanaco`
    `MOOSE_ENDPOINT https://play.semoss.org/moose`
    `#GUANACO_ENDPOINT https://play.semoss.org/moose/guanaco/`
    `GUANACO_ENDPOINT https://play.semoss.org/moose/llama2/`
- Save the changes.

**Install Openai for Python**
- Open the **Command Prompt**, type the following command
`py –[YOUR PYTHON VERSION NUMBER] -m pip install --upgrade openai`

**Note:** YOUR PYTHON VERSION NUMBER is thge python version installed in your machine.

**Start using MooseAI**
- Go to Eclispe and restart your **Tomcat server**.
- Open **CFG instance** in your browser. Log out once and log back in.
- Create a new insight and select the database.
- From the settings below, change the frane type to **Python** and then click on **Import**.

![Python Frame](../../static/img/MooseAI/PythonFrame.png)

- Click on **Visualize the data**, then click on **Add Panel**.
- Click on **Add AI Assistant** and present.

![Add Assistant](../../static/img/MooseAI/AddAssistant.png)
> You should be able to see a chatbot like icon at the bottom of your screen

~![MooseAI Ready](../../static/img/MooseAI/MooseAI.png)
> Moose AI is ready to assist you in your queries.
