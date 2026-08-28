# 🌐 AWS Static Website Deployer

An automated static website deployment tool built using **Python, Boto3, Amazon S3, AWS CLI, and PowerShell**.

The project simplifies the process of deploying static websites to Amazon S3 by automating tasks such as bucket configuration, website file upload, and deployment.

Instead of manually uploading website files and configuring an S3 bucket through the AWS Management Console, the deployment process can be performed programmatically using Python and AWS APIs.

---

# 🚀 Project Overview

Deploying a static website manually can involve several repetitive steps:

1. Creating an S3 bucket
2. Configuring the bucket
3. Preparing website files
4. Uploading HTML, CSS, and JavaScript files
5. Configuring static website hosting
6. Updating files when changes are made

The **AWS Static Website Deployer** automates these operations using Python and Boto3.

The project is designed for static websites that primarily use:

* HTML
* CSS
* JavaScript
* Images
* Other static assets

---

# 🎯 Objectives

The main objectives of this project are:

* Automate static website deployment to AWS
* Reduce manual deployment steps
* Use Amazon S3 for static website hosting
* Upload website files programmatically
* Learn AWS SDK integration using Python
* Practice cloud automation using Boto3
* Make website deployment faster and repeatable
* Provide a foundation for future CI/CD automation

---

# ❗ Problem Statement

When deploying a static website manually, developers may need to repeatedly perform several tasks through the AWS Management Console.

This can become inefficient when:

* Website files are updated frequently
* Multiple deployments are required
* Files need to be uploaded repeatedly
* S3 configuration must be performed manually
* Deployment needs to be reproduced consistently

A scripted deployment process can reduce these repetitive tasks.

---

# 💡 Proposed Solution

The project uses Python and Boto3 to automate the deployment process.

The basic workflow is:

```text
Website Files
     |
     v
Python Deployment Script
     |
     v
AWS Boto3
     |
     v
Amazon S3
     |
     v
Static Website
```

The deployment script communicates with AWS using the AWS SDK and uploads the required website files to an S3 bucket.

---

# ☁️ AWS Architecture

```text
                     Developer
                         |
                         |
                   Run Python Script
                         |
                         v
                  Python + Boto3
                         |
                         v
                  AWS API / SDK
                         |
                         v
                 +---------------+
                 |  Amazon S3    |
                 |               |
                 | Website Files |
                 +---------------+
                         |
                         v
                  Static Website
                         |
                         v
                    Web Browser
```

---

# 🧩 AWS Services Used

| AWS Service / Tool | Purpose                                      |
| ------------------ | -------------------------------------------- |
| **Amazon S3**      | Stores and hosts static website files        |
| **AWS IAM**        | Provides permissions required for deployment |
| **Boto3**          | Python SDK used to communicate with AWS      |
| **AWS CLI**        | Used for AWS management and verification     |
| **Python**         | Implements the deployment automation         |
| **PowerShell**     | Used to run deployment and AWS commands      |
| **Git / GitHub**   | Source-code management and project hosting   |

---

# ⚙️ How It Works

## Step 1: Prepare Website Files

The project starts with a static website containing files such as:

```text
index.html
style.css
script.js
images/
```

These files are placed in the website/project directory.

---

## Step 2: Configure AWS

The Python script uses Boto3 to communicate with AWS.

The AWS environment must have appropriate credentials configured through a secure AWS authentication mechanism.

Credentials should **never** be hardcoded into the Python source code.

---

## Step 3: Create or Configure S3 Bucket

The deployment process uses an Amazon S3 bucket to store the website.

Example bucket:

```text
mairaj-static-website-2026
```

The bucket is configured according to the requirements of the static website.

---

## Step 4: Upload Website Files

The deployment script uploads the website's static assets to Amazon S3.

Example:

```text
Local Website
│
├── index.html
├── style.css
├── script.js
└── images/
       |
       v
Amazon S3
│
├── index.html
├── style.css
├── script.js
└── images/
```

---

## Step 5: Website Hosting

Amazon S3 provides the storage infrastructure required for hosting the static website.

The browser requests the website files from the configured S3 website endpoint or other configured delivery mechanism.

---

# 🔄 Deployment Workflow

```text
                 Start
                   |
                   v
            Prepare Website
                   |
                   v
          Run Deployment Script
                   |
                   v
             Connect to AWS
                   |
                   v
          Configure S3 Bucket
                   |
                   v
           Upload Website Files
                   |
                   v
          Verify Uploaded Files
                   |
                   v
           Access Static Website
                   |
                   v
                  Done
```

---

# 🐍 Python + Boto3

The deployment automation is implemented using Python and the AWS SDK for Python, **Boto3**.

Boto3 allows the application to interact with AWS services programmatically.

The deployment logic can perform operations such as:

```text
Connect to AWS
      |
      v
Access S3
      |
      v
Create / Configure Bucket
      |
      v
Upload Files
      |
      v
Verify Deployment
```

This removes the need to manually perform every deployment operation through the AWS Console.

---

# 📁 Project Structure

A recommended project structure is:

```text
aws-static-website-deployer/
│
├── deploy.py
├── index.html
├── style.css
├── script.js
├── requirements.txt
├── README.md
├── .gitignore
│
└── screenshots/
    ├── s3-bucket.png
    ├── uploaded-files.png
    ├── terminal-deployment.png
    └── website.png
```

> Update the filenames above to match the actual files in your repository.

---

# 🧪 Deployment and Testing

The deployment process can be tested using the AWS CLI and PowerShell.

### Verify AWS Configuration

```powershell
aws sts get-caller-identity
```

This can be used to verify that the AWS CLI is authenticated correctly.

---

### Check S3 Bucket

```powershell
aws s3 ls
```

This displays the available S3 buckets accessible to the configured AWS identity.

---

### Check Website Files

```powershell
aws s3 ls s3://YOUR_BUCKET_NAME/
```

This can be used to verify that website files have been uploaded.

---

### Deployment Verification

After deployment, verify:

* S3 bucket exists
* Website files are present
* `index.html` is available
* CSS and JavaScript files are uploaded
* Website loads correctly
* Browser console does not show unexpected errors

---

# 📸 Project Screenshots

Screenshots can be added to the repository to demonstrate the actual implementation.

## Deployment Terminal

```markdown
![Deployment Terminal](screenshots/terminal-deployment.png)
```

## S3 Bucket

```markdown
![S3 Bucket](screenshots/s3-bucket.png)
```

## Uploaded Website Files

```markdown
![Uploaded Files](screenshots/uploaded-files.png)
```

## Live Website

```markdown
![Live Website](screenshots/website.png)
```

> Make sure screenshots do not expose AWS access keys, secret keys, credentials, private information, or other sensitive configuration.

---

# 🔐 Security

Security is an important consideration when automating AWS deployments.

The project should **never** contain:

```text
AWS Access Keys
AWS Secret Keys
Passwords
Private Keys
.env files
AWS credential files
```

AWS credentials should be configured using secure mechanisms such as AWS CLI credential configuration, environment variables, IAM roles, or other appropriate AWS authentication methods.

The deployment IAM identity should receive only the permissions required for the deployment.

---

# 🛡️ IAM Permissions

The deployment process requires appropriate permissions for Amazon S3.

Depending on the implementation, permissions may include actions such as:

```text
s3:ListBucket
s3:GetObject
s3:PutObject
s3:DeleteObject
s3:CreateBucket
```

Only the permissions actually required by the deployment script should be granted.

This follows the **principle of least privilege**.

---

# 🌐 Static Website Hosting

Static website hosting is suitable for applications that do not require a traditional server-side backend.

Examples include:

* Portfolio websites
* Landing pages
* Documentation websites
* Product showcase pages
* Personal websites
* Simple JavaScript applications

The website consists primarily of client-side resources such as:

```text
HTML
CSS
JavaScript
Images
Fonts
Other static assets
```

---

# 💰 Benefits

## ⚡ Faster Deployment

Automating the upload process reduces repetitive manual work.

## 🔄 Repeatable Deployments

The same deployment process can be executed whenever website files are updated.

## ☁️ Cloud Hosting

The website files are stored in Amazon S3.

## 🛠️ Automation

Python and Boto3 allow AWS operations to be performed programmatically.

## 📈 Scalable Foundation

The project can be extended into a complete CI/CD deployment pipeline.

## 💻 Simple Infrastructure

Static websites do not require a continuously running application server for the website files themselves.

---

# 🆚 Manual vs Automated Deployment

| Manual Deployment                | Automated Deployment          |
| -------------------------------- | ----------------------------- |
| Open AWS Console                 | Run deployment script         |
| Configure S3 manually            | Automate S3 operations        |
| Upload files manually            | Upload files programmatically |
| Repeat steps for updates         | Repeat the deployment command |
| Higher chance of manual mistakes | More consistent process       |
| Time-consuming                   | Faster and repeatable         |

---

# 🛠️ Technology Stack

### Programming

* Python

### AWS

* Amazon S3
* AWS IAM

### AWS SDK

* Boto3

### Development Tools

* AWS CLI
* PowerShell
* Git
* GitHub

### Frontend

* HTML5
* CSS3
* JavaScript

---

# 🌟 Key Features

* ☁️ Amazon S3-based website hosting
* 🐍 Python deployment automation
* 🔧 Boto3 AWS integration
* 📤 Programmatic file upload
* 🔄 Repeatable deployment workflow
* 🔐 IAM-based access control
* 🖥️ AWS CLI verification
* 🌐 Static website deployment
* 📁 Support for common static assets
* 🚀 Foundation for CI/CD automation

---

# 💼 Real-World Applications

This project can be adapted for:

### 👨‍💻 Portfolio Websites

Deploy developer portfolios directly to AWS.

### 🏢 Business Websites

Host static company websites and landing pages.

### 📄 Documentation

Deploy static documentation websites.

### 🎨 Landing Pages

Quickly deploy marketing and promotional pages.

### 🧪 Development Environments

Create simple deployment workflows for development and testing websites.

---

# 🔮 Future Enhancements

The project can be extended with more advanced deployment features.

## 🔄 CI/CD Integration

Integrate the deployment process with:

* GitHub
* AWS CodePipeline
* AWS CodeBuild

This could automatically deploy the website whenever changes are pushed to a repository.

---

## 🌍 Amazon CloudFront

Add Amazon CloudFront to provide:

* Global content delivery
* HTTPS support
* Improved website performance
* Edge caching

---

## 🔒 HTTPS

Use CloudFront with an appropriate TLS certificate to provide secure HTTPS access.

---

## 🔍 Deployment Verification

Automatically verify:

* Required files exist
* Upload completed successfully
* Website is reachable
* Deployment did not fail

---

## ↩️ Deployment Rollback

A future version could maintain previous website versions and provide a rollback mechanism when a deployment introduces an error.

---

## 📊 Deployment Logging

Add structured logging to record:

```text
Deployment Start
Files Uploaded
Files Updated
Files Failed
Deployment Completed
```

---

# 🎓 Learning Outcomes

This project provided practical experience with:

* Amazon S3
* AWS IAM
* Python
* Boto3
* AWS CLI
* PowerShell
* Cloud automation
* Static website hosting
* AWS SDK integration
* File uploads using AWS APIs
* Deployment automation
* Git and GitHub
* Cloud infrastructure concepts

---

# 🏁 Conclusion

The **AWS Static Website Deployer** demonstrates how Python and Boto3 can be used to automate the deployment of static websites to Amazon S3.

Instead of manually performing repetitive AWS Console operations, the deployment process can be executed programmatically.

The project provides a practical introduction to **AWS cloud automation, S3 hosting, IAM permissions, Python SDK development, and repeatable deployment workflows**.

It also provides a foundation for future improvements such as **CI/CD pipelines, CloudFront integration, HTTPS, deployment verification, logging, and automated rollback**.

---

# 👨‍💻 Author

**Mairaj Shaikh**

MCA Student | AWS & Python Developer

---

## 📄 Disclaimer

This project was developed for educational and demonstration purposes.

AWS usage may incur charges depending on the services and configuration used. Always review AWS pricing, IAM permissions, and security settings before deploying resources in a production environment.
