# AUTOMATE INFRASTRUCTURE WITH IAC USING TERRAFORM PART 1

## Table of Contents
- [Introduction](#introduction)
- [prerequisites](#prerequisites)
- [Create an S3 bucket](#create-an-s3-bucket)



## Introduction
In the previous project, we manually implemented an AWS Infrastructure as Code. In this project, we will automate the infrastructure using Terraform. Terraform is an open-source infrastructure as code (IaC) tool created by HashiCorp. Users define and provide data center infrastructure using a declarative configuration language known as HashiCorp Configuration Language, or optionally JSON. Terraform generates an execution plan describing what it will do to reach the desired state and then executes it to build the described infrastructure. As the configuration changes, Terraform can determine what changed and create incremental execution plans which can be applied.
![Infrastructure](https://darey.io/wp-content/uploads/2021/07/tooling_project_16.png)


## Prerequisites
- AWS Account
- AWS CLI installed and configured
- Create an IAM user and name it terraform and ensure you grant it AdministratorAccess permissions also grant it programmatic access
- Configure programmatic access from your local machine to connect to AWS using the access keys generated for the user and a python sdk called boto3.

[Here is a guide on how to create an IAM user and grant it programmatic access](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users_create.html)

[Guide to configure AWS on your local machine using boto3](https://boto3.amazonaws.com/v1/documentation/api/latest/guide/quickstart.html)

result:
![User Terraform](img/user_terraform.png)

## Create an S3 bucket
- Create an s3 bucket to store our Terraform state file.
    - You can name it something like '<yourname>-dev-terraform-bucket'
    Note: Names must be unique within a region partition.
    - Navigate to the S3 service and create a bucket.
    - Select the region you want to use.
    - Specify your bucket name according to the naming convention specified earlier.
    - Ensure you leave block all public access to the bucket checked.
    - Enable bucket versioning.
    - Specify the tag: which can be the name of the bucket.
    - Click on create bucket.


    result:
    ![S3 Bucket](img/s3_bucket.png)