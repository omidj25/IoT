# Cumulocity > WebMethods > AWS S3
In this example we weill send IoT logs from webMethods to AWS S3

## Prerequisites
I. AWS instance running with an available S3 bucket, Access Key and Secret Key will be required when registering Access to your AWS enviroment

II. Cumulocity account with at least 1 registered IoT device 
  
## Set Up

1. Lets start by creating a new workflow from scartch, you should now see a workflow canvas shown below.

<img width="500" alt="canvas" src="https://user-images.githubusercontent.com/52167245/60108670-01297380-9737-11e9-8d4d-4a9fbf3459f9.PNG">

2. Double click the start icon, scroll down the list of triggers and select Cumulocity. You will now be able to set a label name for your Trigger. We will leave the Select Trigger field as "Alarm". If this is your first time connecting Cumulocity, you will have to click the "+" button and enter your Cumulocity Tenant and Credentials(Hover over the lightbulb for examples). Last you will have to enter your device ID(Device ID can be found in Cumulocity under the device information).

<img width="323" alt="cumulocityRegistration" src="https://user-images.githubusercontent.com/52167245/60109133-ce33af80-9737-11e9-813a-494fef3aeabc.PNG">

<img width="274" alt="CumulocityReg2" src="https://user-images.githubusercontent.com/52167245/60109223-fcb18a80-9737-11e9-9deb-aaee958ff836.PNG">

3. Click and drop the AWS icon from the list of application on the right panel onto the canvas. Connect the start icon to the AWS icon and also connect the AWS icon to the end icon.

<img width="370" alt="awsIcon" src="https://user-images.githubusercontent.com/52167245/60109584-99742800-9738-11e9-934b-139913098607.PNG">

4. Double click the AWS icon and from the list of Actions select "S3 Upload File". You will now have to click the "+" sign and connect to your AWS instance by entering the required Keys, when finished click "Add".

<img width="320" alt="aws" src="https://user-images.githubusercontent.com/52167245/60110232-c37a1a00-9739-11e9-9bbd-6c80a58c809a.PNG">

<img width="276" alt="addaws" src="https://user-images.githubusercontent.com/52167245/60110204-b78e5800-9739-11e9-929d-378a9203ab67.PNG">

5. From the mapping screen we will now enter the S3 bucket that you want files uploaded into. We can now also customize the Cumulocity Data we want to recieve and store ina  file for each alarm. In the Example below for the File name I used the Id + _@ + time + .txt (example file name : 37417_@2018-12-18T06:54:20.007Z.txt). In the Raw Data field I added the entire Trigger Data. Click the "Next" button and Test your configured Data. When test has passed click the "Done" button.

<img width="476" alt="mapping" src="https://user-images.githubusercontent.com/52167245/60111059-38018880-973b-11e9-8e96-ccd64aa35e1a.PNG">

6. It is very important to remeber to save your workflow in order to start executing the workflow!

<img width="130" alt="save" src="https://user-images.githubusercontent.com/52167245/60111517-12c14a00-973c-11e9-8dfd-21272ca28b2b.PNG">

7. To test the Flow trigger an alarm from your device, you will see the workflow execute and save the file into your specified S3 bucket.













