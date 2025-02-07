---
sidebar_label: 'Local Backend Installation'
sidebar_position: 1
---

# Local SEMOSS Backend Installation Guide
## Overview
SEMOSS, like most web apps, has a backend and a frontend. The **backend** is responsible for managing the data, models, and running the logic that underpins SEMOSS.
Meanwhile, the **frontend** provides a user interface that allows you to view and interact with SEMOSS in a browser.

You must install both the backend and the frontend in order to run SEMOSS locally. This guide will walk through how to install the backend.
To access the frontend local installation instructions, click [here](Frontend%20Installation.md).

> **Note**
> If you don't need admin privileges and would prefer a **lightweight, low management** way to connect to SEMOSS, then use the [live web server](https://workshop.cfg.deloitte.com/cfg-ai-demo/SemossWeb/packages/client/dist/) instead of following this guide. Instructions to set up a connection to the web version can be found in the [Connecting to SEMOSS](../How%20To/Establish%20Connection%20to%20CFG%20Portal/Connecting%20to%20CFG%20AI.md) guide.

## Local vs. Dockerized: Which one should I choose?
SEMOSS supports two ways of running locally: 
1. [Full local installation](#installation-instructions)
2. [Docker container](Docker%20BE%20Install%20Guide.md)

**Run a full local installation if you:**
* Want the ability to directly modify the core backend source code and configuration
* Want to contribute to the SEMOSS project
* Want to bring your own dependency versions
  
**Run a Docker container if you:**
* Want a prepackaged solution without having to manage and install packages/dependencies locally
* Do not need visibility into core backend logic
* Only plan to create custom backend reactors for your apps

**For most users, it is sufficient to run SEMOSS in a Docker container.** You can still create custom app logic when running SEMOSS in a Docker container. For instructions on how to run SEMOSS with Docker, click [here](Docker%20BE%20Install%20Guide.md). 

This guide will focus instead on the steps for installing and running the SEMOSS backend in a **[full local installation](#installation-instructions)**. 

# Installation Instructions
The installation steps differ slightly depending on whether your operating system is **Windows** or **OSX (Mac)**. Click on one of the below links to jump to the section that matches your operating system.
* [Windows Installation Guide](#windows-installation-guide)
* [OSX (Mac) Installation Guide](#osx-mac-installation-guide)

## Windows Installation Guide

Please click on the link below to find the Windows Installation Guide

*    [Semoss Installation for Windows](../How%20To/Establish%20Connection%20to%20CFG%20Portal/Semoss%20Installation.md#semoss-installation-for-windows)



## OSX (Mac) Installation Guide

Please click on the below link to find Mac Installation Guide 

*    [Semoss Installation for Mac Silicon](../How%20To/Establish%20Connection%20to%20CFG%20Portal/Semoss%20Installation.md#semoss-installation-for-mac-silicon)


## What's Next?
Finished with this guide? 
Head over to the **[Frontend Installation Guide](Frontend%20Installation.md)** to finish setting up your local SEMOSS instance.

If you've already completed the local frontend installation, check out one of the **App Use Case Quick Start guides** linked below to get a hands-on tutorial with your preferred frontend framework!
   - [React Quick Start Guide](../How%20To/App%20Creation%20Guides/React%20App%20Quickstart%20Guide.md)
   - [Using React Locally](../How%20To/App%20Creation%20Guides/React%20App%20In-Depth%20Guide.md)
   - [Sample VanillaJS Use Case](../How%20To/App%20Creation%20Guides/VanillaJS%20App%20Quickstart%20Guide.md)
   - [Sample Streamlit Use Case](../How%20To/App%20Creation%20Guides/Streamlit%20App%20Quickstart%20Guide.md)
