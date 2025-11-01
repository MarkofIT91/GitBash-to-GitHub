Terraform startup Process:

If you've followed the Class 7 install document material, you should have already created your AWS account which includes your Root Account
and your IAM Account and also installed the extensions, apps, software required for class. Once you have done that and set your IAM account 
as your default AWS call back account while working in the CLI, you should be good to proceed. 

Once you have confirmed all of the above is True, open GitBash as Administrator and Verify that the above is all True by following the steps below. GitBash is the designated CLI to be used for the duraion of thi class unless otherwise specified. Do not use PowerShell for this.

I'm using a Windows machine, so this explanation is mainly for windows.

1. In GitBash, to verify your AWS is up to date, run "aws --version"
    - if need be, run "pip3 install awscli --upgrade --user" to ensure you have the latest version of the AWS CLI.
    - If you DO NOT have AWS CLI installed on your machine go back into the Class 7 Start Up Document and begin resolving the issue. Reach out for help if need be.
2. If you do have AWS correctly installed, run "aws configure" in order to see the last four
    characters of the AWS Access Key and Secret Access Key that you have assigned to be associated to your CLI, along with the Default region name and the Default outut format you selected when you generated your AWS account.
    - The Acces Key and Secret Access Key should be referenceing your IAM Account NOT YOUR ROOT Account!! Verify you are NOT referencing your Root Account when you run "aws configure". If you are, go back to the Class 7 Start Up Document for steps to correct this. Reach out for help if need be.
3. At this stage you can begin working on confirming Terraform is properly installed. 
    - Begin by confirming if you have Terraform installed on your machine by running "terraform --version".
    - If you are operating in an earlier verison of terraform, you can run,
    "choco upgrade terraform" to get the latest version.
    - If you do not have Terraform installed run,
    "choco install terraform".
    - After that run "terraform --version" to verify it is installed.
4. Now let's prepare to use Terraform:
    - Still in GitBash as Admin, begin from your Home Directory (~), and navigate to your Class 7 Terraform folder.
    - It is important to remember that Terraform needs you to have the folder open that has your .tf files within it in order for it to operate as intended and expected.
    - Now open Visual Studio Code to the same folder you opened in GitBash as Admin. The folder should be empty, so we can populate it from scratch.
    - Set your VSC terminal default to that of GitBash by opening the terminal within VSC and selecting the terminal dropdown icon and opening the "Select Default Profile" option and choose GitBash. We will be running commands from here going forward.
    - Let's begin by uploading the .gitignore file within our newly created folder in VSC.
        - run the command, "curl -O https://raw.githubusercontent.com/MarkofIT91/class6/refs/heads/main/.gitignore" as this will pull from the URL file path and save the file(s) to the current directory you are in with the same filename you pulled from the server you called to. This .gitignore file prevents sensitive Terraform data from being misused. DO NOT MODIFY OR DELETE THIS FILE!!
    - Next, still within the VSC GitBash terminal, create a new file titled "0-auth.tf" by way of the "touch" command. This will be your authentification file for Terraform which is required for proper operation.
    - Once your 0-auth.tf file has been created AND SAVED, let's now populate the 0-auth.tf file with the following below:

    [provider "aws" {
        region = "us-east-1"
        }

        terraform {
        required_providers {
            aws = {
            source  = "hashicorp/aws"
            version = "~> 3.0"
            }
        }
    }
    ]

    - Save the updates made to the file.
    - Run "terraform init" to start up the Terraform software.
    - This command , if successful, should create a ".terraform" folder and a ".terraform.lock.hcl" file. DO NOT MODIFY OR DELETE THESE FILES!!
    - Now, let's generate another Terraform file titled, 
    "1-main.tf". From here we will generate a code for a basic VPC resource. Populate the 1-main.tf file with the code below:

    [resource "aws_vpc" "Terraform_VPC" {
        cidr_block = "10.234.0.0/16"
        tags = {
            Name = "basic-vpc"
        }
    }
]

    - Run "terraform validate" to see if the current configuration is valid.
    - Run "terraform plan" to compare your infrastructure to your configuration of what your code intends to perform.
    - Run "terraform apply" to begin creating the VPC resources called for creation.
    - If successful, a ".terraform.tfstate" file was also created. DO NOT MODIFY OR DELETE THIS FILE!!
    - Screenshot of successful "terraform apply"
    ![Successful terraform apply](image.png)
    - Screenshot of successful "aws sts get-caller-identity" command, which displays your current AWS account info in use to carry out these tasks.
    ![AWS Identity confirmation](image-1.png)
    - Screenshot of the .gitignore file in the shared folder with terraform files.
    - ![.gitignore and .tf files](image-2.png)
    - I shared my documentss with (Insert Name Here) and they were successful in deploying Terraform on their machine.

    