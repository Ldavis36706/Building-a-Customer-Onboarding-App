# Building-a-Customer-Onboarding-App
I was tasked with building a customer onboarding app. The project spans over the course of 10 weeks. Each week I made progress towards completing the app. 


<h2>Description</h2>
In your first capstone, you are a cloud application developer working for AnyCompany Bank. The bank has decided to develop and deploy a customer onboarding application on AWS. During customer onboarding, there is a significant exchange of information between AnyCompany Bank and customers. Customer onboarding allows AnyCompany Bank to obtain documentation to meet regulatory requirements and provide relevant products and services to customers. Your task is to help AnyCompany Bank build a customer onboarding application on AWS. With the proposed customer onboarding solution on AWS, AnyCompany Bank can use artificial intelligence (AI), machine learning (ML), and digital tools to streamline the onboarding process. With these solutions, AnyCompany Bank can transform how they onboard customers and reduce friction during this essential process.


<br/>

<h2>Languages and Utilities Used</h2>

- <b> Amazon S3: </b> Amazon S3 is an object storage service that offers industry-leading scalability, data availability, security, and performance. It stores and protect any amount of data for a range of use cases, such as data lakes, websites, built-for-the-cloud applications, backups, archives, machine learning, and analytics.
- <b> IAM: </b> AWS Identity and Access Management (IAM) is a web service that helps you securely control access to AWS resources. With IAM, you can centrally manage permissions that control which AWS resources users can access. You use IAM to control who is authenticated (signed in) and authorized (has permissions) to use resources.
- <b> AWS Cloud9 IDE: </b> AWS Cloud9 is a cloud-based integrated development environment (IDE) that lets you write, run, and debug your code with just a browser. It includes a code editor, debugger, and terminal. AWS Cloud9 comes prepackaged with essential tools for popular programming languages, including JavaScript, PHP, Python, and more, so you don’t need to install files or configure your development machine to start new projects.
- <b> Amazon EC2: </b>  The virtual server (Ubuntu Linux instance) hosting the Apache2 web server.
- <b> Apache2: </b> The web server that served the webpage.
- <b> Linux Commands (via Bash): </b>  Used for troubleshooting and configuring the server, moving files, and running system commands (e.g., systemctl to check Apache2 status).
- <b> Amazon SNS: </b> Amazon Simple Notification Service (Amazon SNS) is a managed service that provides message delivery from publishers to subscribers (also known as producers and consumers). Publishers communicate asynchronously with subscribers by sending messages to a topic, which is a logical access point and communication channel. Clients can subscribe to the Amazon SNS topic and receive published messages using a supported endpoint type, such as Amazon Data Firehose, Amazon SQS, AWS Lambda, HTTP, email, mobile push notifications, and mobile text messages (SMS).
- <b> DynamoDB: </b> Amazon DynamoDB is a fully managed NoSQL database service that provides fast and predictable performance with seamless scalability. DynamoDB lets you offload the administrative burdens of operating and scaling a distributed database so that you don’t have to worry about hardware provisioning, setup and configuration, replication, software patching, or cluster scaling. DynamoDB also offers encryption at rest, which eliminates the operational burden and complexity involved in protecting sensitive data.
- <b>AWS Lambda: </b> AWS Lambda is a compute service that lets you run code without provisioning or managing servers. Lambda runs your code on a high availability compute infrastructure and performs the administration of the compute resources, including server and operating system maintenance, capacity provisioning and automatic scaling, and logging. With Lambda, all you need to do is supply your code in one of the language runtimes that Lambda supports.
- <b>AWS SAM: </b> AWS SAM consists of two parts, AWS SAM templates and the AWS SAM CLI. AWS SAM templates provide a shorthand syntax, optimized for defining infrastructure as code (IaC) for serverless applications. An extension of AWS CloudFormation, you deploy AWS SAM templates directly to CloudFormation, benefiting from its extensive IaC support on AWS. The AWS SAM CLI is a developer tool that puts AWS SAM features at your fingertips. Use it to quickly create, develop, and deploy serverless applications.
- <b> Amazon Rekognition: </b> Amazon Rekognition is a cloud-based image and video analysis service that makes it easy to add advanced computer vision capabilities to your applications. The service is powered by proven deep learning technology, and it requires no machine learning expertise to use. Amazon Rekognition includes a simple, easy-to-use API that can quickly analyze any image or video file that’s stored in Amazon Simple Storage Service (Amazon S3).

<h2>Environments Used </h2>

 <b>Cloud Platform:
AWS (Amazon Web Services): This project was conducted entirely in AWS, utilizing several of its services.
</b> 
<h2>Program walk-through:</h2>

<p align="center">

<h2><u>Week 1:</u></h2>

![Figure 1](https://github.com/user-attachments/assets/99a58b86-a85f-4efa-a465-51d0c99f93ed)

<b><i>Image description: The diagram depicts the KYC application architectural diagram. The diagram highlights the key resources that you need to create and configure in this lab. These two resources are the Document S3 bucket and the Document Lambda function IAM role.</b></i>

<h1></h1>

My first week I created an Amazon Simple Storage Service (Amazon S3) bucket to store the customers’ documents, I configured the bucket policy, and created an AWS Identity and Access Management (IAM) role with specific permissions to access the S3 bucket. 
<br/> <strong>VERY IMPORTANT:</strong> You must create the permissions <b>**BEFORE**</b> creating the role. You attach the permissions to the role when it's created so it's important to create the permissions first. 

![Creating Permissions for Lambda role](https://i.imgur.com/mVchuJh.png)

<h2><u>Week 2:</u></h2>

![Figure 2](https://github.com/user-attachments/assets/c9f55f55-c4f4-4c45-8427-05e4a2f37060)

<b><i>Image description: The diagram depicts the KYC application architectural diagram. The diagram highlights the key resources that you must create and configure in this lab. These resources are the Customer DynamoDB table, the Document Lambda function IAM role, and the SNS topic.</i></b>

<h1></h1>

<h4></h4>
My second week I created an Amazon DynamoDB table to store customer data, created an Amazon Simple Notification Service (Amazon SNS) topic to send application notifications, and add DynamoDB and Amazon SNS permissions to the AWS Lambda function AWS Identity and Access Management (IAM) role.
<br/> <strong>VERY IMPORTANT:</strong> You should consider provisioning the capacity mode so that it can auto scale when hitting target utilization. For the onboarding app I set both the read and write capacity to a <b> minimum of 2  units </b> and a <b> maximum of 20 units </b> with <b>70%</b> target utilization.  
<br/>

![Creating Dynamo DB table](https://i.imgur.com/g0Q0uxn.png)

<b><i>Image description: The Amazon Dynamo table was created successfuly and named "CustomerMetadataTable".</i></b>

<h1></h1>

After you create an Amazon Simple Notification Service topic, be sure to subscribe to the notification. <strong>VERY IMPORTANT:</strong> You should confirm your subscription to receive the notifications.

![SNS Notifications](https://i.imgur.com/n16tsYy.png)

<h2><u>Week 3:</u></h2>

![Figure 3](https://i.imgur.com/kSwrUXN.png)
<b><i>Image description: The diagram depicts the KYC application architectural diagram. The diagram highlights the key resources that you must create or configure in this lab. These two resources are the Document Lambda function and the Document Lambda function IAM role.</b></i>

My third week I added new permissions to the AWS Lambda function role. I got started with the AWS Cloud9 environment to develop the application code, and created a Lambda function and configured its settings. Also, I configured an Amazon Simple Storage Service (Amazon S3) event notification to invoke the Lambda function. 

<h1></h1>

AWS Lambda automatically monitors Lambda functions on your behalf, pushing logs to Amazon CloudWatch. To help you troubleshoot failures in a function, after you set up permissions, Lambda logs all requests handled by your function and automatically stores logs generated by your code through Amazon CloudWatch Logs. However, to monitor the output of your Lambda function, you first must give permissions to the function to write logs to CloudWatch Logs. I added the necessary permissions. Next, AWS Cloud9 environment I added code to that will upload files to the S3 bucket I created in Week 1.

![Adding Code to Upload files to S3](https://i.imgur.com/jT6EQfC.png)

<b><i>Image description: Python code that upload files to the S3 bucket created in week 1.</b></i>

<h1></h1>

The Lambda function I created is invoked when a .zip file containing the customer information, license image, and selfie image is uploaded into the Document bucket.

![Creating Lambda function](https://i.imgur.com/PPRs8b5.png)

<b><i>Image description: I created the Lambda function.</b></i>


<h1></h1>

I tested the functionality of the Lambda function by creating a folder named "zipped" in my Document Bucket. I uploaded a file to the bucket and then I checked the Cloudwatch logs to verify the function was invoked. 

![Checking CloudWatch Logs](https://i.imgur.com/S3rA4Jx.png)

<b><i>Image description: The CloudWatch logs verify that the Lambda function was invoked.</b></i>

<h1></h1>

The customer onboarding process starts by the customer using a mobile app to apply as a new customer to the bank. The customer, through the mobile app, enters personal details, uploads a driver’s license ID image, and takes a selfie. The mobile app writes the customer information into a .csv file, and then generates a unique identifier, denoted as app_uuid, for each customer. Then, the mobile app archives the customer details, driver’s license ID, and selfie into a .zip file and uploads it to the zipped/ prefix in the S3 bucket.

Lastly for this week, I started developing the first task performed by the DocumentLambdaFunction to download the .zip file from the bucket and extract its contents to start processing and validating the customer details. The DocumentLambdaFunction code shoud do the following:
- <b>	Download the .zip file object from zipped/ prefix in the S3 bucket.</b> My code should know the .zip file name from the invocation event that I captured in the previous task.
- <b>	Extract the .zip file into the /tmp directory in the Lambda function ephemeral storage. </b>
- <b>	Upload the three extracted files to the unzipped/ prefix in the Documentbucket. </b> 



I made the changes and tested it by uploading a zipped file and ensured that it's contents where moved to an unzipped folder. 

![Upload Zipped File](https://i.imgur.com/BmdMjLK.png)

<b><i>Image description: I uploaded a zipped file to invoke the Lambda function. The Lambda function uploaded all three individual files to the unzipped/ prefix in the S3 bucket.</b></i>

<br/>

<h1></h1>

I further developed the Lambda function so that it interacts with Amazon S3 events. The function now does the following: <br/>
- <b>	Extract the app_uuid value from the file name. </b>I saved it into a variable named app_uuid.
- <b>	Extract the unzipped selfie file object name in the unzipped/ prefix in the S3 bucket. </b> 
- <b> Extract the unzipped driver’s license file object name in the unzipped/ prefix in the S3 bucket. </b> The key should include the prefix, as well. 
- <b>	Extract the local details file name in the Lambda function. </b>

<br/>
I tested the funtion by uploading a zipped file to the S3 bucket. Then I checked the CloudWatch logs to verify that it's abstracting the values from the files. 

![Abstracted Values in Cloud](https://i.imgur.com/nUW8iZq.png)

<b><i>Image description: CloudWatch is abstracting the values from the files that are uploaded to S3.</b></i>

<h2> Week 4: </h2>

![Figure 4](https://i.imgur.com/ayGVJRw.png)
<b><i>Image description: The diagram depicts the KYC application architectural diagram. The Document Lambda function that you will build in this lab is highlighted.</b></i>



  





