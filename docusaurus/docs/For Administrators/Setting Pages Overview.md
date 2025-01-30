# Settings
You can find the Settings icon at the bottom left corner of the platform.

![Settings](../../static/img/Settings.png)

In the Settings section, you have give or revoke access of any App, Model, Function, Database, Vector, or Storage of which you are an author. You can even edit the type of access given to other practisioners, like changing the access from author to an editor or just a viewer. Below mentioned is the difference between the 3 types of permission.

## Permission Levels

As mentioned in the section above, there are 3 separate permission levels that a user can choose from. For most resources, the majority of users with access should be Editors or Read-Only.

> **Note**:
> Turnaround time for access is **variable**. Currently all access has to be approved by a user with **Author** privileges.

**Author**  
An author user has the ability to edit an App or the resource and to also grant users access to the app/resource. On a given team, only one or two people should have Author level privileges. This is to limit the amount of people that are able to change the resource.

**Editor**  
An Editor has access to the app/resource and can freely make pixel calls to query the resource. This should be the base level that is given to most users, especially to developers who want to create Gen AI apps that utilize the SEMOSS server.

**Read-Only**  
This level of access should only be given to users who are meant to demo already created applications. They will be unable to generate new data but can see any generated data.

## App Settings

When you click on the App Settings tab, you will see all the apps that are housed under the 'My Apps' section in your platform.

![AppSettings](../../static/img/Applist.png)

To change the access settings of any App, click on it. You will have to be an author of the app to edit the access settigs. If you are an author, you can either add members, revoke access from any existing members, or edit the access type.

![Member](../../static/img/Members.png)

### Pending Request

You can also see if there are any Pending requests from any practisioners. If there are any requests, you can either approve or reject them. You can even control the type of access given (author, editor, or viewer).

![Pendingrequest](../../static/img/Pendingrequest.png)

### Data Apps

> To be added

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

## Model, Function, Database, Vector, Storage Setting

Settings for all the resources works in the same way as it is for App Settings. The only difference is that in these 5 resource settings you will not find the 'Data Apps' tab. Apart from this, all features and functuality remains the same.

## Jobs

> To be added

## My Profile

Here you can view your profile details like Name, Email, your ID.

![Access token](../../static/img/Settings/profileinfo.PNG)

The important function housed in My Profile section is that of **Personal Access Token**. You can use this section especially if you a frontend developer and want to access Semssos backend. To do this you need to create a **access key** and a **secret key**.

For this, click on + New Key, highlighted in the image below.

![Access token](../../static/img/Settings/personalaccesstoken.PNG)

Give a name to your request and add a description (optional) and hit generate.

![Access token](../../static/img/Settings/generatekey.PNG)

Once you hit generate, you will be able to see your 'Access Key' and 'Secret Key'. Please note that you can view your secret key only once so make sure you copy it and save it somewhere.

Once you click 'close', you will return to the 'My Profile' page. Now you will see your access tokens with your Access Key mentioned (but not your secret key).

Now to connect to Semoss backend, you need to write a code in your .env file. The code to write is mentioned on the 'My profile' page, just you need to paste the keys (access and secret) and you are good to go.

![Access token](../../static/img/Settings/codesample.PNG)

