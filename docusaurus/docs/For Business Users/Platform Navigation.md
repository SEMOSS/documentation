# Platform Navigation
CFG AI is a platform that enables developers to create Gen AI (Generative AI) applications at the client level and deploy within the enterprise. It manages logging, monitoring, metering, and access management so that developers can focus on business problems. It consists of App Library, Functions, Models, Database, Vector, and Storage.

In this section we are going to see how to navigate through the platform and its different resources and what all the platform has to offer. When you login to the Cfg.Ai Platform, you arrive at its homepage as illustrated in the picture below.

![Home Page](../../static/img/PlatformNavigation/HomepagePN.png)

Here, on the leftmost side you will see your App Library along with the 5 platform resources. These are briefly described below,
1. App Library - Repository of all the Apps you create and have access to use
2. Function - 
3. Model - We connect our Apps to Models which are LLMs 
4. Database -
5. Vector -
6. Storage -

----------------------------------------------

# SEMOSS Overview

SEMOSS is a platform that enables developers to create Gen AI (Generative AI) applications at the client level and deploy within the enterprise. It manages logging, monitoring, metering, and access management so that developers can focus on the business problem. It consists of App Library, Models, Database and Storage. In this section we are going to go through how to add to and populate your SEMOSS instance. 

## App Library
App Library is a section in SEMOSS which consists of list of Gen AI applications present on the platform and are created by user. Once you click on a particular app in the App Library, it will open the App which is ready to use. App Library also let developers create Gen AI applications by adding App details and uploading code for the app.

<ReactPlayer controls url={AppLibraryIntro} />

## Adding a Model 
Models are LLMs (Large Language Model) which is a type of AI (Artifical Intelligence) algorithm that uses deep learning techniques and massively large data sets to understand, summarize, generate and predict new content. Gen AI Apps created on SEMOSS are built on these models. 

To connect to existing Models or add new Models, click on the **vector** icon on the left side of SEMOSS portal which will take you to Model catalog.

![App Library](../../static/img/Navigating/CFG%20AI%20Walkthrough/ModelCatalogIconHighlight.PNG)
> _Highlighted icon for Model Catalog_

Once you're in the current Model Catalog, you will find a list of LLMs that already accessible to you. If you do not have any existing LLMs in your current model catalog, you can go to **Discoverable models**, browse through the available models and request access:

![Model Catalog](../../static/img/Navigating/CFG%20AI%20Walkthrough/Add_Model.PNG)
> _"Add Model" Button_

Click on **Add Model**, chose your model of choice from the list and fill in the details to connect to the model.

![Add Model](../../static/img/Navigating/CFG%20AI%20Walkthrough/Connect_To_Model.PNG)
> _Various Model Options_

<ReactPlayer controls url={ModelCatalog} />

There are primarily three types of models available with different characteristics:

**Commercially-hosted -** These are managed by an external vendor and comes with a subscription or licensing fee. The vendor handles hosting and maintenance. These models are highly scalable and customizable.

**Locally-hosted -** These are installed and managed on the organization's own servers attached with a subscription or licensing fee. This means the organization is in full control of the model and can customize the model as per the requirements.

**Embedded -** These kind of models are integrated with other softwares or platforms focused on specific functions. These can be blended seamlessly into the existing system.

## Adding a Storage Source
Storage is used to store data that is created while using Gen AI Apps on SEMOSS. There are a number of options on which Storage can be hosted (eg- Amazon S3, Google Cloud Storage, Dropbox etc). 

To connect to existing Storage or add new Storage, click on the **box** icon on the left side of SEMOSS portal which will take you to Storage catalog.

![Storage icon](../../static/img/Navigating/CFG%20AI%20Walkthrough/StorageCatalogIcon.PNG)
> _Highlighted icon for Storage Catalogue_

Once you're in the Storage Catalog, you will find Storage if they are already present and accessible by you as shown below.

![Storage Catalogue](../../static/img/Navigating/CFG%20AI%20Walkthrough/Add%20Storage.PNG)
> _"Add Storage" button_

For adding, click on **Add Storage** and it will take you to **Connect to Storage** page where you will find number of Storage options to chose from as illustrated below.

![Add Storage](../../static/img/Navigating/CFG%20AI%20Walkthrough/Storage%20Options.PNG)
> _Various Storage Options_

Click on the **Storage option** which you want for your instance. In this case, we will click on **MINIO** and it will take you to the page where you have to fill out the Storage details.

![Enter Storage Details](../../static/img/Navigating/CFG%20AI%20Walkthrough/Storage%20Details.PNG)
> _Storage Details Required_

Please fill in the details below to connect a test MINIO storage source.

**Name** - CFG-demo

**Region** - us-east-1

**Access Key** - cfgaidemo

**Secret Key** - ENcgT9q9

**End Point** - http://34.118.228.102:9000

**Root Bucket Path** - demo-bucket

Click on **Add Storage** shown at the bottom of details page and Storage will be added to the Storage Catalog as shown in below snapshot.

![Storage Catalogue 2](../../static/img/Navigating/CFG%20AI%20Walkthrough/Storage%20Catalogue.png)
> _Newly added Storage_

<ReactPlayer controls url={StorageCatalogDemo} />

### Using a Storage Source
These commands demonstrate how to use the storage engine via the Terminal app and within any apps that you create. These commands are not to be confused with the SDK which are seperate.  

```
# Initialize the storage engine  
from gaas_gpt_storage import StorageEngine
storageEngine = StorageEngine(engine_id = "2d905aa3-b703-4c98-8133-5bcaefddac1e", insight_id = '${i}')  
```  
```
# List the files on your storage path  
storageEngine.list(storagePath = "my_s3_storage_path")  
```  
```
# List the files on your storage path with extra details  
storageEngine.listDetails(storagePath = "my_s3_storage_path")  
```  
```
# Sync'ing your local folder to the specified storage directory
# Space can be the project id, "user" or "insight"
# This is where the local path starts
# So in this case, the local path starts in the project directory
storageEngine.syncLocalToStorage(storagePath="my/s3/storage/path", localPath="/my/local/dir", space="my_project_id")  
```   
```  
# Sync'ing your storage directory to the local folder
# Space can be the project id, "user" or "insight"
storageEngine.syncStorageToLocal(storagePath="my/s3/storage/path", localPath="/my/local/dir", space="my_project_id")  
```  
```  
# Upload a folder or file from your local project/insight/user directory to the specified storage directory
storageEngine.copyToStorage(storagePath="my/s3/storage/path", localPath="/my/local/dir", space="my_project_id")  
```  
```  
# Download a folder or file from the specified storage directory to your local project/insight/user directory
storageEngine.copyToLocal(storagePath="my/s3/storage/path", localPath="/my/local/dir", space="my_project_id")  
```  
```  
# Delete a folder or file from the specified storage directory
storageEngine.deleteFromStorage(storagePath = 'your/storage/file/path', leaveFolderStructure=False)  
```  


## Adding a Database
Databases are organized data that is linked with Gen AI Apps on SEMOSS and can be used by those Apps to use data. Databases enable Apps to provide results as per requirement. You can create a new database or add locally available databases to SEMOSS which can be then connected to Apps.

### Pre-requisites
- Before adding a Database to your SEMOSS instance, it must be detached from any existing instance otherwise it might return an error.
- When you attach a Database, all data files for the Database must be available

To connect to an existing Database or add a new Database, click on the **cylinderical** icon on the left side of SEMOSS portal which will take you to Data catalog.

![Database icon](../../static/img/Navigating/CFG%20AI%20Walkthrough/Database%20icon.PNG)
> _Highlighted icon for Database Catalogue_

Once you're in the current Data Catalog, you will find a list of Database that are already accessible by you as shown below.

![Database catalog](../../static/img/Navigating/CFG%20AI%20Walkthrough/Add%20Database.PNG)
> _"Add Database" button_

To connect to a Database, click on **Add Database** and you will be directed to the **Add Source** page which will have various options within the Database section mentioned below.

![Add Database](../../static/img/Navigating/CFG%20AI%20Walkthrough/Database%20Options.PNG)
> _Different Options of using Database_

Click on **Connect to Database** icon and it will take you to a page where you will have different Database file types to upload and Types of **Connections** to chose from (shown below).

![Connect to Database](../../static/img/Navigating/CFG%20AI%20Walkthrough/Various%20Database%20type.PNG)
> _Various Database types to choose from_

You can choose the type of file to upload and then choose the **Connections** type based on your Database or requirements. Once you click on the Connections type, it will direct you to a page where you can fill all the required details as shown in the below image. Click on **Connect** at the bottom of the page.

![Database Connection Double Click](../../static/img/Navigating/CFG%20AI%20Walkthrough/Database%20Details%20required.PNG)
> _Database details required to be filled_

<ReactPlayer controls url={DatabaseCatalog} />

## Adding a Vector Database
A vector database is a specialized solution designed for the storage, indexing, and retrieval of massive datasets containing unstructured data. These databases leverage machine learning models and their embeddings to facilitate searching across various forms of unstructured data, including images, video, text, audio, and more. This is done with the help of pixel calls.

To connect to a vector database, go to **App Library > Vector Catalog** and then manually add the vector database.
![Vector_icon](../../static/img/Navigating/CFG%20AI%20Walkthrough/Vector%20Catalog%20Icon.PNG)
> Click on vector icon
  
Click on **Add Vector** on the top-right section and it will take to different type of connections for Vector.

![Add_Vector_Manually](../../static/img/Navigating/CFG%20AI%20Walkthrough/Add%20Vector.PNG)
> Adding vector manually

Choose an appropriate **Connection** based on your requirements.
![ConnectYourVector](../../static/img/Navigating/CFG%20AI%20Walkthrough/Choose%20a%20connection.PNG)
> Choosing connection

Fill in the required details. Click on **Add Vector**.
![AddDetails](../../static/img/Navigating/CFG%20AI%20Walkthrough/Add%20Vector%20Details.PNG)
> Fill in the details and click create vector

Your vector database is now ready to use. 

Now to embed your vector database with some data, **Click** on it to open.
![Vector Catalog](../../static/img/Navigating/CFG%20AI%20Walkthrough/NewVectorCatalog.png)

You will see 4-5 tabs within your database depending upon your access privileges. Go to **Files**.

Click on **+ Embed New Document** to upload your data file. It only accepts files with .txt, .csv, ,pdf, .doc, .ppt extensions.
![Embed Data](../../static/img/Navigating/CFG%20AI%20Walkthrough/NewEmbedData.png)

Click on **upload files** to select and upload your data and click on **Embed**. You can also drag and drop your file to the same window.
![Upload Files](../../static/img/Navigating/CFG%20AI%20Walkthrough/NewUploadData.png)

You should now be able to see your file inside the vector database.
![Data Files](../../static/img/Navigating/CFG%20AI%20Walkthrough/NewDataFiles.png)

If you have questions regarding the policies or your datasets, go to **Q&A** tab and type in your query in the space provided.
![Q&A Tab](../../static/img/Navigating/CFG%20AI%20Walkthrough/NewQ%26ATab.png)

Once the file is uploaded, run the following command.

`CreateEmbeddingsFromDocuments ( engine = "80a482d5-06b7-4ff6-bedc-0d0570b7bfeb" , filePaths = [ "TestFile.csv" ] , paramValues = [ { "columnsToIndex" : [ "content" ] } ] ) ;`

![EmbedDB](../../static/img/VectorDatabase/EmbedDB.png)
> Execute this command to embed your vector database with the .csv file

* This will take a while to run. Once completed, your vector database is ready to use.
  
> **Note**
> The engine ID above needs to match the engine ID of the vector database you just created.

* To do so, go back to App Library > Vector Catalog by clicking the vector icon on the left-side.

![Vector_icon](../../static/img/Navigating/CFG%20AI%20Walkthrough/Vector%20Catalog%20Icon.PNG)
> Look for the database you just created.

<ReactPlayer controls url={VectorCatalogDemo} />

## Access to resources
**Discoverable items** in catalogs are the resources which are created by other users and present on SEMOSS portal. You need to request access to those resources to use them.

![Discoverable Items](../../static/img/Navigating/CFG%20AI%20Walkthrough/Discoverable%20Items.PNG)
> _Discoverable Models_

To get access to any Model, Database, or Storage, click on that resource and it will direct you to that resource page as shown below.

![Request Access](../../static/img/Navigating/CFG%20AI%20Walkthrough/Request%20Access.PNG)
> _Request access to Model_

Click on **Request Access** near the top-right corner and a pop-up will provide you with 3 options to choose from - Author, Editor & Read-Only. You can choose the option based on your role and request.

![Grant Permission](../../static/img/Navigating/CFG%20AI%20Walkthrough/Permission%20Levels.PNG)
> _Permission Levels_

### Permission Levels

As mentioned in the section above, there are 3 separate permission levels that a user can choose from. For most resources, the majority of users with access should be Editors or Read-Only. 

> **Note**:
> Turnaround time for access is **variable**. Currently all access has to be approved by a user with **Author** privileges. 

**Author**  
An author user has the ability to edit the database and to also grant users access to the resource. On a given team, only one or two people should have Author level privileges. This is to limit the amount of people that are able to change the resource. 

**Editor**  
An Editor has access to the database and can freely make pixel calls to query the resource. This should be the base level that is given to most users, especially to developers who want to create Gen AI apps that utilize the SEMOSS server. 

**Read-Only**  
This level of access should only be given to users who are meant to demo already created applications. They will be unable to generate new data but can see any generated data. 

### Inside the resource

Once you click on the resource (Model, Database, Storage etc.), you will be directed into the resource page where you will see **Overview**, **Usage**, **Metadata** and **Settings** tabs.

**Overview**  
This tab consists of information related to the resource, like technical details, versions, and model type. Tagging and Domain details are also included in this section.

**Usage**  
This tab consist of code in **Pixel**, **Python** and **Java**. You can copy and use the code in any of the languages based on your Application code.

**Metadata**  
This tab is present in **Database** only and consists of information related to data present in the Database.

**Settings**  
This tab is present in **My Resources** and consists of adjustable settings related to resource. You can also add or remove members and give them permissions by their role. There is also an option to edit SMSS properties within the **Settings** tab. 

## Removing an App from SEMOSS

If you ever want to remove an App from your SEMOSS server, the first thing that you should do is navigate to your settings sections (the gear). 

![Settings Tool](../../static/img/Navigating/CFG%20AI%20Walkthrough/Settings%20Tool%20icon.PNG)
> _The settings tool_

Inside Settings, you should see a screen that has a settings sections for each of the resources you have in SEMOSS. Click on App Settings. 

![App Settings](../../static/img/Navigating/CFG%20AI%20Walkthrough/CfGAI%20Settings_2.PNG)
> _This will house all the Gen AI apps that you have in your App Catalog_

Here you will see each of your apps listed individually. Click on the app that you would like to delete. 

![App Catalog in Settings Page](../../static/img/Navigating/Navigating3.PNG)
> _All of your Apps displayed_

Once inside an app, you can easily delete it by clicking the delete button. 

![Delete Button](../../static/img/Navigating/Navigating4.png)
> _Delete Button_

> **Warning**:
> This will **delete** the App for all users! 

This process can be replicated for all other resource types (databases, models, storage catalogs, etc) in SEMOSS! 

<ReactPlayer controls url={RemovingApp} />

## Commonly Asked Questions

* **What should we do if we encounter errors while using the platform?**

    For immediate issues, please take a screenshot of the error and share it via Teams, including the URL bar for context. If the error message is related to system capacity, such as limited GPU space, try again later or opt for a managed model.

* **Can models and other endpoints be called from outside environment like AWS compute or local system?**

    Yes, you can use the SDKs to set up authentication to access the resources in another environment. Please refer to the following page for more information: 
[How to establish connection to CFG Portal](../../How%20To/Establish%20Connection%20to%20CFG%20Portal/OpenAI%20Endpoints%20with%20Python.md)

* **In models, can we edit parameters like temperature, etc.?**

    Yes, temperature and other parameters can be set up for models. Please refer to the following page for more information:
[Playground App](../../Get%20Started/Navigation/Apps%20in%20CFG%20AI.mdx#3-playground.md)

* **How can we find descriptions of each model available?**

    Model descriptions are available in the metadata of each model.

* **How do we access different models and choose the most relevant one as per our needs?**

    It is recommended to experiment with various models to see which aligns best with your data. Navigate Model Overviews and use Tags to narrow your selection based on specific use case.

* **What is the difference between 'Commercially Hosted', 'Locally Hosted', and 'Embedded' models?**

    **Commercially Hosted**: Models like OpenAI and AWS Titan are closed systems.
    **Locally Hosted**: Ideal for clients who wish to use open-source models and maintain control over their data.
    **Embedded**: Typically involves fine-tuned models running directly within the same container, useful for specific data processing tasks.  

* **How long does model response typically take?**

    Response times vary based on server load and the complexity of the query.

* **How do we select the appropriate embedder for our documents?**

    Choose an embedder based on the type of documents you are working with and prior data on which embedder has been trained to ensure accuracy and relevance in results.

* **Can we extract a string of text from an image in a document (e.g., a PDF)?**

    There is an optional routine we can run with a image to text model which not just extract the text but can also interpret the image so one can semantically search images. However, due to poor GPU capabilities, it is not exposed yet.

* **How many files/documents can be ingested into a vector database?**

    This depends on the size of the files, specific hardware and the environment. 

* **How do we add documents to a vector catalog? Is it similar to training a RAG?**

    Adding documents involves embedding and indexing them within the catalog, its different from training a RAG (Retriever-Answer Generator).

* **Can vectors created in one model be utilized across other models?**

    Yes, vectors are typically interoperable across models, but effectiveness can depend on the similarity of the data types they were trained on.

* **Does each vector database connection (like Pinecone, FAISS etc.) use their own embedding methods like TFIDF or bag of words?**

    One can define the embedding method they want to use when creating a vector database.

* **Can a vector database be moved to a GCP environment or we should use a cloud native tool for that?**

    One can utilize a vector database hosted within a VPC or a cloud native tool as well.

* **Do vector databases support CSV/Excel files directly or do we need to consider additional things if we are using CSV/Excel files in vector database?**

    CSV/Excel files can be uploaded to a vector database, but there are some additional things that need to be provided for how these should be parsed. E.g, is it a column with text that you want to add? Are all columns concatenated together?

* **Can a new document be added to an already available database?**

    Yes, in the "Files" tab of the vector database, one can add or remove documents. Please see the following page for more information: [Adding a vector Database](../../Get%20Started/Navigation/CFG%20AI%20Walkthrough.mdx#adding-a-vector-database.md)

