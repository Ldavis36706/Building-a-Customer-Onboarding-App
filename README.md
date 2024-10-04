# Building-a-Customer-Onboarding-App
In your first capstone, you are a cloud application developer working for AnyCompany Bank. The bank has decided to develop and deploy a customer onboarding application on AWS. During customer onboarding, there is a significant exchange of information between AnyCompany Bank and customers. 


<h2>Description</h2>
In your first capstone, you are a cloud application developer working for AnyCompany Bank. The bank has decided to develop and deploy a customer onboarding application on AWS. During customer onboarding, there is a significant exchange of information between AnyCompany Bank and customers. Customer onboarding allows AnyCompany Bank to obtain documentation to meet regulatory requirements and provide relevant products and services to customers. Your task is to help AnyCompany Bank build a customer onboarding application on AWS. With the proposed customer onboarding solution on AWS, AnyCompany Bank can use artificial intelligence (AI), machine learning (ML), and digital tools to streamline the onboarding process. With these solutions, AnyCompany Bank can transform how they onboard customers and reduce friction during this essential process.


<br />

<h2>Languages and Utilities Used</h2>

- <b> HTML: </b> For creating the basic webpage, including hyperlinks, an HTML entity, and a favicon.
- <b> Bash: </b> For running commands in the AWS Cloud9 terminal (e.g., verifying the Apache2 service, moving files).
- <b> AWS Cloud9 IDE: </b> Integrated development environment where the web server was configured and the webpage was created.
- <b> Amazon EC2: </b>  The virtual server (Ubuntu Linux instance) hosting the Apache2 web server.
- <b> Apache2: </b> The web server that served the webpage.
- <b> Linux Commands (via Bash): </b>  Used for troubleshooting and configuring the server, moving files, and running system commands (e.g., systemctl to check Apache2 status).


<h2>Environments Used </h2>

 <b>Cloud Platform:
AWS (Amazon Web Services): This project was conducted entirely in AWS, utilizing several of its services.
</b> 
<h2>Program walk-through:</h2>

<p align="center">

I begin this lab by creating and configuring the Document S3 bucket and Document Lambda function IAM role resources. These resources are highlighted in the following diagram.

<br/>

![Figure 1](https://github.com/user-attachments/assets/99a58b86-a85f-4efa-a465-51d0c99f93ed)

<b><i>Image description: The diagram depicts the KYC application architectural diagram. The diagram highlights the key resources that you need to create and configure in this lab. These two resources are the Document S3 bucket and the Document Lambda function IAM role.</b></i>
