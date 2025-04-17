![image](https://github.com/user-attachments/assets/73060794-6614-483b-9126-5ac31a64a883)# MULTI-CLOUD-ARCHITECTURE

**COMPANY**: CODTECH IT SOLUTIONS

**NAME**: YUVRAJ VISHVANATH MUDLIYAR

**INTERN ID**: CODHC203

**DOMAIN**: CLOUD COMPUTING

**DURATION**: 12 WEEKS

**MENTOR**: NEELA SANTOSH

#DESCRIPTION

Step 1: Build Your Backend on Azure
1.	Login to Azure Portal
https://portal.azure.com
2.	Click on Create a Resource Group -> Click on Create  Function App -> Select the Consumption Plan
3.	on Resource Group option -> Click Create new resource group -> azureAwsInteropRG
4.	On Function App ->  multi-cloud-azure-aws
5.	On Operating System -> Select the Windows
6.	On Runtime stack -> Select the Node.js
7.	On version -> Select the 20 LTS
8.	On region -> Select the West Europe
9.	Click on Review + Create

    
Step 2: Write a Function 
•	Go to your Function App: multi-cloud-azure-aws
•	Under Functions Tab -> Click on Create function-> Click on HTTP Trigger -> Click on Next -> Automatically Function name and Authorization level appear by default – just Click on Create
•	By default it generate the Function code for HTTP Trigger
You can Check it, If you want to Customize you can customize and after all changes  Click on Save 
Then click on Get Function URL  Copy the default (Function key) URL and paste in the index.html on the place of fetch(“”)


Step 3: Allow Origin on Azure 
•	Go to your Function App: multi-cloud-azure-aws
•	In the left menu, Search CORS and click “CORS”
•	Under Allowed Origins, add this: http://multi-cloud-demo-bucket.s3-website-us-west-2.amazonaws.com 
•	Click on Save


Step 4: Build the Frontend on AWS (S3 Static Website)
•	Prepare the HTML File
Create an index.html file on your computer with the following content (update the Azure Function URL):

<!DOCTYPE html>
<html>
<head>
  <title>Multi-Cloud Interoperability Demo</title>
</head>
<body>
  <h2>Frontend (AWS S3) → Backend (Azure Function)</h2>
  <button onclick="callAzure()">Call Azure Function</button>
  <p id="response">Response will appear here...</p>
  <script>
    function callAzure() {
      fetch("https://multi-cloud-azure-aws.azurewebsites.net/api/HttpTrigger1?code=xtOf61mKzZVBhtPamHaLeJ4Erm1nrV5e2t3GET1ot7JTAzFuHzML-w==")
        .then(response => response.text())
        .then(data => {
          document.getElementById("response").innerText = data;
        })
        .catch(error => {
          document.getElementById("response").innerText = "Error: " + error;
        });
    }
  </script>
</body>
</html> 

Step 5: Set Up an S3 Bucket for Static Website Hosting
1.	Login to AWS Console → https://console.aws.amazon.com
•	Go to S3 → Click Create Bucket
•	Bucket name: multi-cloud-demo-bucket
•	Region: Same as where you want to deploy (can be any)
•	Disable Block all public access (for testing/demo)
•	Click Create Bucket

2.	Upload Your HTML File which created above index.html
•	Click on your bucket → Go to Objects → Click Upload
•	Upload your index.html file
•	After upload, go to Permission on Bucket-level -> Click On Edit Object Ownership-> Click on ACLs enabled -> Click on Checkbox of I acknowledge that ACLs will be restored. -> Click on Save Changes→ Go to the Object Tab -> Select the File -> Actions → Make public using ACL -> Click on Make Public

3.	Enable Static Website Hosting
•	In your S3 bucket, go to Properties
•	Scroll to Static website hosting
•	Enable it
•	Hosting Type Select Host a static website
•	Set index.html as the index document
•	Click on Save Changes
•	Copy the Bucket website endpoint URL provided

4.	Test the Setup
•	Visit the S3 static website URL in your browser -> http://multi-cloud-demo-bucket.s3-website-us-west-2.amazonaws.com
•	Click the "Call Azure Function" button
•	You should see: "👋 Hello, Azure! This HTTP triggered function executed successfully from Azure. " (or your custom message)





#OUTPUT
![image](https://github.com/user-attachments/assets/bc057fb2-d488-411b-878b-c1dbc926f937)


![image](https://github.com/user-attachments/assets/760bd820-248d-4e34-9848-20653c96cdec)


![image](https://github.com/user-attachments/assets/c2607472-d752-402b-9000-c8bf9eab096a)



![image](https://github.com/user-attachments/assets/e9fef8ef-d0e8-46ff-86ab-bc6ab47f604e)



![image](https://github.com/user-attachments/assets/017cac6a-4ff7-484b-9e47-7e76bbbb6236)


![image](https://github.com/user-attachments/assets/e56ff46b-bfe7-4286-802c-04aad1c57840)


![image](https://github.com/user-attachments/assets/1e7b2c0b-294c-4e20-a7e2-778fe89f5f78)


![image](https://github.com/user-attachments/assets/007175e9-d9e1-4299-8778-d80ac06db4f4)


