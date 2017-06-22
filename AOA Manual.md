
# AOA Manual<br>－<b>A</b>dd <b>O</b>utbound change sets <b>A</b>utomatically 

[toc]

## Intorduction
You may have suffered from adding hundreds components one by one before each deployment. It's an extremely boring stuff. It's very simple but takes time, so this task is very suitable for automation by programming. That's why I developed this simple tool.


## Download AOA
### [Download from Google Drive](https://goo.gl/PDyzNw)

## Before starting creating *outbound change set*
1. Check if the *AOA* folder contains
	* AOA.exe
	* AOAconfig.ini
	* chromedriver.exe
	* Component List.csv
2. Verify the URLs of *OutboundChangeSet* wrote in *AOAconfig.ini*  
	For now, the URL of STG is 
```https://trendmicro--stg.cs30.my.salesforce.com/changemgmt/listOutboundChangeSet.apexp?retURL=%2Fui%2Fsetup%2FSetup%3Fsetupid%3DDeploy&setupid=OutboundChangeSet```
URL of Beta is 
```https://trendmicro--beta.cs51.my.salesforce.com/changemgmt/listOutboundChangeSet.apexp?retURL=%2Fui%2Fsetup%2FSetup%3Fsetupid%3DDeploy&setupid=OutboundChangeSet```
But it might be changed after refresh.

3. Prepare the list of components
You can follow the format of the CSV file(Component List.csv)
Here is an example list:
| Component Type<br>(required) | API name<br>(required)	| Object<br>(if need) |
| ------------- | --------- | ---- |
|Page Layout|TS Contact Page Layout|Contact|
|Page Layout|TS Contact Page Layout w MSI|Contact|
|Static Resource|ideas||
|Static Resource|ideasRAW||
|Workflow Rule|TS Open Case Age > 30 Days||
|Workflow Email Alert|TS Open Case Age > 30 Day||
|Custom Field|AC_SN|Invoice Details|
|Custom Field|Co-Term|Invoice Details|
|Language Translation|Japanese||

## Start adding the component
Steps:
1. Open the AOA.exe
![enter image description here](http://i.imgur.com/C7ghIIz.png)
2. Choose the environment, STG or Beta? (Don't forget to check if the URL in *AOAconfig.ini* is correct)
![enter image description here](http://i.imgur.com/96eaRQ9.png)
3. Login to Salesforce with your own username and password
![enter image description here](http://i.imgur.com/DXhh4AB.png)
4. (if needed) Receive email and enter the verification code
![enter image description here](http://i.imgur.com/TjIGnlx.png)
5. This program will run automatically after logging in successfully
6. Wait for a moment. The time varies with the number of components.
7. Check the items when AOA finish. You also can review the log.txt for detail.
![enter image description here](http://i.imgur.com/OqJVwus.png "Check items")
![enter image description here](http://i.imgur.com/sHAAp5a.png "log.txt")