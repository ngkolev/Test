# Create Your First Module 

## Overview
Creating Kognifai applications has its specifics, as is the case with any other platform. In order to ease the burden on developers we provide a Visual Studio project template to give them a useful starting point and create the basic artefacts required by Kognifai. 

This guide assumes that you are running a development instance of Kognifai and have completed the necessary steps to successfully do so. 
QuickStart

#### Step 1. Set up the Development Environment
To install the Poseidon Tools extension for Visual Studio download Kognifai template extensions.vsix from 

https://github.com/kognifai/GST-Intruments/tree/master/Visual%20Studio%20Extensions 
and start it.

#### Step 2. Create a new project

After that you can simply create a new Poseidon Application from Visual Studio (version 2017) which will provide us with basic necessary files required by a Kognifai application. 
To create a new application project, choose the New Project option and select the Poseidon Application template in the TypeScript section. Enter the name of the project. For example SamplePoseidonApp:

 

#### Step 3: Start the application

Now we need to build our new project. 

When the build finishes right-click on the project from the source in the solution explorer. Choose Properties and then Web from the left navigation menu:

 
Select Local IIS from the dropdown and enter the correct path to Poseidon local IIS instance + the base path to application files Server/Modules/SamplePoseidonApp. 

We need to use the Poseidon Module Installer tool in order to register our new application. In the generated project there is already a cmd script that invokes the installer. First we need to ensure that the path to Poseidon.Module.Installer.exe is correct in the install-module.cmd file located in the newly created project:

```
@ECHO OFF
SET moduleInstaller="Disk:\%PoseidonSourceDir%\Platform\DEV\Poseidon.Module.Installer\bin\Debug\Poseidon.Module.Installer.exe"
SET manifest=SamplePoseidonApp.manifest.json
CALL %moduleInstaller% install %manifest%
PAUSE

```

Then simply run install-module.cmd and “Module installed successfully” message should be shown.

In order to open the new application, just browse your local Kognifai Application Framework instance using your favorite browser. Depending on the installation steps the Kognifai Application Framework instance is typically on http://localhost or http://localhost:8080. Log in with the username admin and password poseidon. You can see the application in the main menu. It contains a single page with some text.

We have created a very basic Kognifai application.
