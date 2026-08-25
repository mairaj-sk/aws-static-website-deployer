# aws-static-website-deployer
A Python and Boto3-based CLI tool that automates static website deployment to Amazon S3, including bucket management, file uploads, content-type configuration, public read access, and static website hosting.
-------------------------------------------------------------------------------------------

1. Why did we build this project?

Normally, if you want to host a static website on Amazon S3, you have to manually:

Create an S3 bucket
Configure the bucket
Upload HTML/CSS/JavaScript files
Set the correct content types
Configure static website hosting
Configure the required access policy
Find the website endpoint
Repeat these steps whenever the website changes

Doing all of this manually is time-consuming and repetitive.

Our project automates these operations using Python + Boto3.

Instead of manually performing everything, you can run:

python deploy.py

and select:

5. Deploy Complete Website

The application performs the deployment automatically.

2. How does this project help?

The main benefit is automation.

For example, imagine a developer has a website containing:

index.html
style.css
script.js

Every time the website is updated, they could manually upload the files to S3.

With our tool:

Developer
    ↓
python deploy.py
    ↓
Select "Deploy Complete Website"
    ↓
S3 Bucket
    ↓
Website Files Uploaded
    ↓
Website Hosting Configured
    ↓
Live Website

So the developer doesn't have to repeat the AWS Console process every time.

3. What problem does it solve?
Problem

Manual deployment to cloud storage can involve several repetitive configuration steps and can lead to mistakes such as:

Uploading files to the wrong bucket
Incorrect Content-Type
Forgetting to configure website hosting
Forgetting required permissions
Repeating the same configuration manually
Solution

Our Python application provides a repeatable deployment process.

It automatically:

Verifies/creates the S3 bucket
Uploads website files
Detects file types
Configures Content-Type
Configures static website hosting
Configures public read-only access
Displays the website URL
4. Technologies used
Programming
Python 3.13
Boto3
Frontend
HTML5
CSS3
JavaScript
Cloud
Amazon S3
AWS IAM
Tools
AWS CLI
PowerShell
Git
GitHub
5. Main features
🔹 1. S3 Bucket Management

The application checks whether the bucket already exists.

If it doesn't exist, it creates the bucket.

🔹 2. Automatic Website Upload

Instead of manually selecting files, the application scans:

website/

and automatically uploads the files.

For example:

website/
├── index.html
├── style.css
└── script.js

becomes:

S3 Bucket
├── index.html
├── style.css
└── script.js
🔹 3. Automatic Content-Type Detection

The application automatically identifies the appropriate MIME type.

For example:

index.html → text/html
style.css  → text/css
script.js  → application/javascript

This helps the browser correctly interpret the files.

🔹 4. Static Website Hosting

The application configures S3 to use:

index.html

as the website's home page.

🔹 5. Public Read-Only Access

The website objects are made publicly readable so visitors can access the website.

The policy grants:

s3:GetObject

rather than giving public users upload or delete permissions.

🔹 6. CLI Menu

The project has an interactive menu:

1. Create / Verify S3 Bucket
2. Upload Website
3. Configure Static Website
4. Configure Public Read Access
5. Deploy Complete Website
6. Show Website URL
7. Exit

This makes the tool easier to use.

6. Real-world use

This project can be useful for developers who frequently deploy simple static websites.

For example:

Portfolio websites

A developer can deploy their portfolio to S3.

Landing pages

Companies can deploy marketing or campaign landing pages.

Documentation websites

Static documentation can be hosted on S3.

College projects

Students can automate cloud deployment instead of manually configuring AWS.

Small business websites

Simple HTML/CSS/JS websites can be deployed without maintaining a traditional web server.

7. Why S3?

Amazon S3 is useful for static websites because the website consists of files such as:

HTML
CSS
JavaScript
Images

There is no requirement for a traditional application server for this type of site.

So instead of maintaining:

EC2 Server
   ↓
Operating System
   ↓
Web Server
   ↓
Website

we can use:

S3
 ↓
Website Files
 ↓
Visitors

This makes the architecture simpler for a static website.

8. Project architecture

Use this in your GitHub README:

                 Developer
                     │
                     │
              python deploy.py
                     │
                     ▼
             Python + Boto3
                     │
                     │ AWS API
                     ▼
              ┌──────────────┐
              │  Amazon S3   │
              │              │
              │ index.html   │
              │ style.css    │
              │ script.js    │
              └──────┬───────┘
                     │
                     │
             Static Website
                     │
                     ▼
                Web Browser

IAM is used to control the AWS permissions required by the deployment process.

9. GitHub repository name

I recommend:

aws-static-website-deployer
Repository description

Use this:

Python and Boto3 CLI tool for automating static website deployment to Amazon S3.

Topics/tags

Add:

aws
amazon-s3
boto3
python
cloud-computing
static-website
aws-s3
automation
cloud-deployment
cli
10. What you should upload to GitHub

Your repository should look like:

aws-static-website-deployer/
│
├── deploy.py
├── requirements.txt
├── README.md
├── .gitignore
│
└── website/
    ├── index.html
    ├── style.css
    └── script.js
Do NOT upload:
venv/

and never upload AWS credentials.

Your .gitignore already handles the venv folder.

11. GitHub upload steps

Open PowerShell inside:

E:\AWS\aws-static-website-deployer
Step 1: Check Git
git --version

If it shows a Git version, you're ready.

Step 2: Initialize Git
git init
Step 3: Check files
git status

Make sure venv/ is not listed.

Step 4: Add files
git add .
Step 5: Check again
git status

You should see your project files staged.

Step 6: Create first commit
git commit -m "Initial project setup"
Step 7: Create GitHub repository

On GitHub, create:

aws-static-website-deployer

For the first push, I recommend not creating another README, .gitignore, or license on GitHub because you already have those files locally.

Step 8: Connect local project to GitHub

GitHub will give you a repository URL. Then you'll run something like:

git remote add origin YOUR_GITHUB_REPOSITORY_URL

Then:

git branch -M main

And:

git push -u origin main
12. What to write on your LinkedIn/resume

This project is also useful for your resume.

Resume version

AWS Static Website Deployer | Python, Boto3, Amazon S3

Developed a Python-based CLI tool to automate static website deployment on Amazon S3. Implemented automated S3 bucket management, website file uploads, MIME type detection, static website hosting configuration, public read-only access, and deployment URL generation using Boto3.

Skills demonstrated
Python
Boto3
Amazon S3
AWS IAM
AWS CLI
Cloud Automation
Static Website Hosting
Git/GitHub
