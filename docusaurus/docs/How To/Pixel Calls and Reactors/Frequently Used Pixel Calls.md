---
sidebar_label: 'Frequently Used Pixel Calls'
sidebar_position: 1
---

# Frequently Used Pixel Calls

## What is a Pixel Call
Pixel is a domain specific language (DSL) specific to CFG AI that is used as the payload for all the operations that can be performed on an insight. Every Pixel has a java class to handle the business logic on the backend, we call this java class a "Reactor".

## How do you write a Pixel Call
A Pixel call has some important components:
1. PixelCommand the name of the pixel logic to execute
2. Inputs
    1. Inputs may use keys to define them
        ```
        AddColumn(newCol=["ColA"], dataType=["VARCHAR(50)"]);
        ```
    2. If PixelCommands do not use keys, then the order of the inputs is important!
       ```
        POWER(2, 3);
        POWER(3, 2);
        ```
3.  Some Pixel commands use pipes (“|”). A pipe is used to indicate that you would like to chain a Pixel command with a previous one. Essentially, the output of one reactor is taken and put into the next reactor so that the Pixel commands build off of each other.
4.  Finally, a semi-colon (“;”)! A semicolon is a terminator and will be found at the end of your chain of commands. A semicolon indicates that you want to create a sink. It is best to create a sink when you are at a logical endpoint, meaning you do not need to use the output of your command for another reactor. For example, a logical endpoint is when you want to push your data to the frontend of CFG AI so that it can be viewed.

## List of Useful Pixel Calls 
There are many pixels calls/commands available that allows us to perform various kinds of tasks. To get a comprehensive list of all available Pixel commands, simply type `Help()` into the console. 
![Help](../../../static/img/Pixel%20Calls/Help1.PNG)

### Common Pixel Calls
#### Engines

* **CreateModelEngine():** This allows you to setup and configure a new LLM into your backend. You can specify the type of model and other details using 2 input parameters.
    - *Input 0:* `model` - Fill in the name/ engine ID of the model you want to use within ("").
    - *Input 1:* `modelDetails` - Provide the map or collection of data that speciifes details to establish connection with the model engine within (""), each element separated by a coma(,).

* **CreateStorageEngine():** This allows you to setup and configure a new storage engine into your backend. You can specify the type of storage and other details using 2 input parameters.
    - *Input 0:* `model` - Fill in the name/ engine ID of the storage you want to use within ("").
    - *Input 1:* `modelDetails` - Provide the map or collection of data that speciifes details to access and interact with the storage engine within (""), each element separated by a coma(,).

* **CreateVectorDatabaseEngine():** This allows you to setup and configure a new vector database engine into your backend. You can specify the type of storage and other details using 2 input parameters.
    - *Input 0:* `database` - Fill in the name/ engine ID of the database you want to use within ("").
    - *Input 1:* `conDetails` - Provide the map or collection of data that speciifes details to establish connection with the database within (""), each element separated by a coma(,).
    - *Input 2:* `filePaths` - Any additional around file paths that may be required.


#### GenAI
* **CreateEmbeddingsFromDocuments()** This allows you to generate embeddings from data or documents that are already stored in your backend. 
    - *Input 0:* `engine` - Fill in the name/ engine ID that you want to use for embedding data within ("").
    - *Input 1:* `filePaths` - Provide the file path or data sources from which you want to create embeddings within (""). 
    - *Input 2:* `paramValues` - Depending on the engine that you're using, you might have to specify additional parameters or options within ("") separating each parameter/option by a coma(,).

* **LLM():** This allows you to run query on any chosen LLM and interact with the underlying workspace.
    - *Input 0:* `engine` - Fill in the name/ engine ID of the model you want to run your queries on within ("").
    - *Input 1:* `command` - Provide the query or command than you want to execute within ("").
    - *Input 2:* `context`- Specify the directory for running the queries within("").
    - *Input 3:* `paramValues` - Define parameter names and their corresponding values within ("") separating each parameter by a coma(,).

#### Accessing Data

* **Database():** This allows you to specify the database that you want to use or identify it as a different variable, example `X = Database ()`.
    - *Input 0:* `engine` - Fill in the name/ engine ID of the database you want to refer within ("").

* **Frame():** This allows you to specify and define a frame/ container for organizing and arranging your data into tables, charts, and other visual formats.
    - *Input 0:* `frame` - Provide the name/ ID of the frame that you want to work with within ("").

* **Insert():** This allows you to insert or add data, values, or text into something. 
    - *Input 0:* `into` - Specify the target or destination where you want to insert any value or data.
    - *Input 1:* `values` - Provide the numeric or string values that you want to insert to be used as input
    - *Input 2:* `commit` - To commit or finalize the insertion.
    - *Input 3:* `customSuccessMessage` - You can define a custom success message that will be displayed after the insertion  is successfully completed

#### Running scripts
* **Py():** This allows you to run custom Python scripts in your backend. This command does not require specific input keys, typically included in the script itself.

* **Command():** This allows you to execute shell commands within your backend.
    - *Input 0:* `command` - Provide the command that you want to run. Commands supported are
        - `cd`
        - `dir`
        - `ls`
        - `copy`
        - `cp`
        - `mv`
        - `move`
        - `del <specific file>`
        - `rm <specific file>`
        - `git`

#### API Calls
* **PostRequest():** This allows you to send a POST request to a specified URL.
    - *Input 0:* `url` - Provide the URL to which yo want to send the POST request.
    - *Input 1:* `headersMap` - Provide the map map containing key-value pairs the send in the headers in the POST request.
    - *Input 2:* `bodyMap` - Provide the map map containing key-value pairs the send in the body of the POST request.
    - *Input 3:* `useApplicationCert` - Use a boolean value to indicate whether the default application certificate should be used when making the POST request.

* **GetRequest():** This allows you to send a GET request to a specified URL.
    - *Input 0:* `url` - Provide the URL to which yo want to send the GET request.
    - *Input 1:* `headersMap` - Provide the map map containing key-value pairs the send in the headers in the GET request.
    - *Input 2:* `useApplicationCert` - Use a boolean value to indicate whether the default application certificate should be used when making the GET request.
    - *Input 3:* `saveFile` - Use a boolean value if you expect the request to return a file, and whether you want to save the file in your the insight space.

* **SendEmail():** This allows you to send emails from one recipient to the other. You can learn more about the inputs for this command using `--help` function.
  
### How to use Help Function
To understand the pixel calls/commands and their input options, you can run the `--help` function. 
1. Type the name of the command you're interested in, followed by two hyphens and the word **help**. 
    - For example, to know about the input options for **CreateModelEngine** command, you'd enter `CreateModelEngine --help` in the console.
![Help1](../../../static/img/Pixel%20Calls/help2.png)

2. You can see all the **Inputs** listed in the console output.



