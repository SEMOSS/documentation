---
sidebar_label: 'By Agent Builder'
sidebar_position: 1
slug: '/agent-builder'
---

# Using Agent Builder to Create a New App

Agent Builder is one of the types of Drag and Drop feature. When we need to develop an app in which the user will enter some input data and the app will provide the corresponsding output, we use the Agent Builder feature. Agent Builer needs only a prompt to create UI for such type of an app.

In Agent Builder, we develop the initial UI by creating a prompt which contains the type of inputs the user will provide and what output is expected out of the app. Once this initial UI is created, an Agent Builder App is no different from Drag and Drop App. Let's understand the process to develop an app via Agent Builder.

To use Agent Builder, first click on **Create New App\* button on the top right corner of your SEMOSS home page and then click on **Get Started\*\* on the Agent Builder tab.

![AB](../../static/img/Navigating/Create%20New%20App/AB1.png)

## Create a Prompt

### Prompt Details

In this section, we give a name to our yet-to-be-defined prompt. Then we assign a tag for our prompt. By asigning a tag we categorise the App as per its function. For example, if we are creating a App for helping users create a travel itinerary, we can give tag as **travel guide**, **itinerary creator**, etc. You can assign multiple tags.

Next we select an model (LLM) which we want the prompt to run through and provide the output to the user (as per the input entered).

![AB](../../static/img/Navigating/Create%20New%20App/AB2.png)

### Define the prompt

Here we will write the actual prompt. This prompt will define the input options we will give to the user and how the UI of our App will look like. To write a prompt assume you are talking to the App. Assume the App to be a living being and tell it about itself (for example for an itinerary creator app we will write- Suppose you are a travel agent). So we give information on what does the App do. Also include what inputs the user will provide to the App and what output should the app then finally present.

![AB](../../static/img/Navigating/Create%20New%20App/AB3.png)

For example, please see below a sample prompt for a travel guide app,
Prompt- Suppose you are a travel agent. The user will provide with the destination, number of days of travel, and their travel pace preference (slow or fast). Prepare an itinerary for them.

So in the above example we told the App about itself. Mentioned what all inputs the user will provide. And told the App what is expectd out of it.

Now, the inputs that we are letting the user decide are called input parameters. And we need to tell the App what all things we want to define as input parameters (which user will provide data for). To do that, include the input parameters inside double curly brackets \{\{ \}\}. By this the app knows that these things the user will provide as input parameters. So, our sample prompt will actually look like,

Prompt- 'Suppose you are a travel agent. The user will provide with the \{\{destination \}\}, \{\{number of days \}\} of travel, and their \{\{travel pace \}\} preference (slow or fast). Prepare an itinerary for them.'

You can even define the input parameters under the 'Define input' section. Just click on the word you want to create as a input parameter. However in this method you won't be able to create an input parameter with multiple words. For example- you can assign 'destination' as an input parameter but no 'number of days'. So it is recommended to use the curly brackets method only.

![AB](../../static/img/Navigating/Create%20New%20App/AB4.png)

### Define the input parameter

Here you can define the type of the input parameter you have selected. Selected any among the different options provided in dropdown.

![AB](../../static/img/Navigating/Create%20New%20App/AB5.png)

### Set Constraints

Here you can set constraints for the output. Examples include limiting responses to a certain number of words, should the output be in bullet points or not, etc.

![AB](../../static/img/Navigating/Create%20New%20App/AB6.png)

Click on Preview to save your settings. You will be direct to the preview of the App. Click on Create App to complete creating the app. You will be directed the UI page where you will be able to see the input parameters that you created. Once you enter inputs for these prompts, the App will run through the model and provide an output.

## Post the initial app development

### Editing the prompt

It is possible to edit the original prompt you have created. To do this, go to your app in the App library. Click on edit in the top right corner.

![AB](../../static/img/Navigating/Create%20New%20App/AB7.png)

Now go to the Data tab and click on Notebooks tab and then on **Prompt Query**. Here, inside the query (highlighted by blue colour in the image below) we can edit the original prompt. Save the changes so it reflects in the UI.

![AB](../../static/img/Navigating/Create%20New%20App/AB8.png)

### Editing the UI tab or Data tab

Using Agent Builder, by just providing a prompt, we can develop the entire app. This puts the UI in place and also creates the required queries (notebooks) and the required variables in the **Data tab**. However, you can edit the UI by adding more blocks (or even removing the existing ones) or by adding more queries (notebooks) or even by creating variables. This process is exactly similar to the Drag and Drop app.

Thus, if we want to edit the **UI tab**, by adding different blocks like HTML or Iframe or an Image, then we can follow the steps mentioned in the documentation of Drag and Drop app. Please click on the link below for this.

- [To be added](#To-be-added)

However, if we want to the edit the **Data tab** by adding more queries or variables it is recommended to delete this app and use the Drag and Drop feature to create an app. Please find its documentation in the link below.

- [To be added](#To-be-added)
