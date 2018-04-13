# Installing Platform Application

This section explains how to install and deploy Platform application in your Windows system. During Installation, the setup program walks you through following stages:

- Before you Begin
- Enable IIS Routing
- Download and install MS SQL Server
- Installation and configuration 

## Before you begin

Before you begin the installation process, the setup runs a prerequisites check in the target system to ensure that it meets all the requirements of the installation and configuration of Application Framework and GST Package.
1.	Locate the installation file folder in your system and select the Setup folder from the Drop folder to begin installation.
2.	Run Setup.exe 

Once the installation process begins, the setup will check the status of prerequisites in your system.

## Setup Prerequisites

You can see what is missing from the necessary prerequisites under Check setup perquisites screen, see the sample image below:

 
You can manually install the components required for the setup based on the information displayed During Check Setup Prerequisites. The steps to install the missing component are given below. Refer : 
  
3.	Run InstallIIS10.bat file to enable necessary Windows Features. 

Note- The IsntallIIS10.bat file is best suited to Windows10, however,  to access the  installation files for Windows 7 and Windows 8, Click here: 
-Or-

You can also check this status manually by using “Check Setup Prerequisites” option on the left menu under Setup steps, (See the image above), or by clicking on Check button at the bottom of the screen. 
Then go ahead by adding missing components/software manually to continue the installation process.
4.	Click Next
5.	Turn On/Of the features under Windows Features screen as per the installation requirements. 







## SamplePoseidonApp.module.ts:

```
module SamplePoseidonApp {

    function registerApplicationState($stateProvider: ng.ui.IStateProvider) {
        $stateProvider.state('6cebe3af-27de-4304-9a66-7cfa105f278d', {
            url: '/SamplePoseidonApp',
            templateUrl: '/SamplePoseidonApp/mainView.html'
        });
    }

    function registerMenuItems(navigationService: Poseidon.INavigationService) {
        var appMenu = new Poseidon.NavigationItem('6cebe3af-27de-4304-9a66-7cfa105f278d', '6cebe3af-27de-4304-9a66-7cfa105f278d', null, 'SamplePoseidonApp.Title');

        // add subitems to the application menu item
        //appMenu.add(new Poseidon.NavigationItem(<menu item id>, <menu item state>, <menu item icon>, <menu item label>));

        // register the application menu item with the navigation service
        navigationService.registerApplication(appMenu);
    }

    angular.module('SamplePoseidonApp', ['Poseidon'])
        .config(registerApplicationState)
        .run(registerMenuItems);
```











