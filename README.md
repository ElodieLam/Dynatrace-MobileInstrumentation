# DynatraceMobileInstrumentation
 
## with Dynatrace 

1.	Select Deploy Dynatrace in the navigation menu.
2.	Click the Set up mobile monitoring button. You'll be redirected to a page where you enter the name of your mobile application.
3.	Once you've provided a name for your app, click Create mobile app. This step creates a new mobile app within Dynatrace.

Choose Google Android / Command line
And copy the value:
•	DTXapplicationID 
•	DTXbeaconURL

## with Android Studio

For each “TODOs”, copy and paste the following code lines

### Open the file MyApplication/app/build.graddle

#### TODO 0 – Add Dynatrace mobile agent dependency (line 32)
implementation 'com.dynatrace.agent:agent-android:7.+'


### Open the file MyApplication/app/src/main/java/com/example/myapplication/MainActivity.java

#### TODO 1: Start the OneAgent (line72)
Dynatrace.startup(this, new DynatraceConfigurationBuilder("b763f69a-f01d-4b58-b914-18fcc40740ae", "https://bf89185syo.bf-sprint.dynatracelabs.com/mbeacon")
        //Here you can add configurations
        .buildConfiguration());

And apply the Dynatrace value for these parameter 
Paste the value 
•	applicationID 
•	beaconUrl


#### TODO 2: Start the User action “GET CURRENT SCORE” (line 91)
DTXAction clickAction = Dynatrace.enterAction("Click on GET CURRENT SCORE button");

#### TODO 3: Identify the user (line 96)
Dynatrace.identifyUser(userId);

#### TODO 4: End the User action (line 98)
clickAction.leaveAction();

#### TODO 5: Start the User action “Click on CATS” (line 109)
DTXAction clickAction = Dynatrace.enterAction("Click on CATS button");

#### TODO 6 – Identify the user (line 118)
Dynatrace.identifyUser(userId);

#### TODO 7 – End the User action (line 121)
clickAction.leaveAction();

#### TODO 8 – Start the User action “Click on DOGS” (line 131)
DTXAction clickAction = Dynatrace.enterAction("Click on DOGS button");

#### TODO 9 – Identify the User (line 140)
Dynatrace.identifyUser(userId);

#### TODO 10 – End the User action (line 143)
clickAction.leaveAction();


### Run the application and create activity.

