# action
First of all you need to create new repository on GitHub or you can use your old repository also

Step#1:Create Docker file for NodeJS App
We have to make a Dockerfile for our application
Step#2:Make a package.json file
Step#3:Create Workflow in GitHub Actions
Now configure the GitHub Actions. For the Image building and pushing it to AWS ECR and here we are going to use a great tool from GitHub called GitHub Actions.
Steps: Steps represent a sequence of tasks that will be executed as part of the job steps

Job: Name: Check out code

It job simply checks out our GitHub repository for “Dockerfile” to build the docker image

Job: Name: Configure AWS credentials

In this job we need to configure AWS login Credentials. For accessing the AWS ECR we need to define a custom Role in later steps.

Job:Name: Build, tag, and push image to Amazon ECR

In this step we are going to build the Docker Image by copying using the Code in our Repository, tagging the Image with Version and pushing Image to AWS ECR 

Step #4:Create Repository AWS ECR
Firstly go to your AWS account and go to ECR and then create a repository and fill the input field and create repository
Step #5:Create Secrets in GitHub
Now to access our AWS ECR, so here we need to add AWS secrets for AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY

So go to the settings and create secrets and set them as Environment Variables.
Note: Your IAM user has proper valid IAM permissions. Your IAM user must have “AmazonEC2ContainerRegistryFullAccess”
Step #6:Build & Push Docker Image to AWS ECR Using GitHub Actions

