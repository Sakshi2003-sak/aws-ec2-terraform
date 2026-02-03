Add AWS EC2 manual and Terraform documentation

🚀 How to Create an EC2 Instance Manually (Step-by-Step)

Step 1: Log in to AWS Console
Open a web browser.
Go to Amazon Web Services.
Click Sign in to the Console and log in with your AWS account.

Step 2: Open the EC2 Service
In the AWS search bar, type EC2.
Click on EC2 from the results.
You will be redirected to the EC2 dashboard.
Click Launch instance.

Step 3: Provide an Instance Name

Step 4: Choose an AMI (Operating System)
Select Amazon Linux 2 AMI (Free Tier Eligible).
An AMI defines the operating system for the EC2 instance.

Step 5: Choose an Instance Type
Select t2.micro.

Step 6: Create a Key Pair
In the Key pair (login) section, click Create new key pair.
Enter the key pair name:

Step 7: Configure Network Settings (Security Group)
Click Edit under Network settings.
Configure inbound rules:
Type: SSH
Protocol: TCP
Port: 22
Source: My IP

Step 9: Launch the Instance
Review all configurations.
Click Launch instance.
Your EC2 instance will be created successfully.


🚀 EC2 Instance Creation Using Terraform (Infrastructure as Code)
What is Terraform?
Terraform is an Infrastructure as Code (IaC) tool used to create and manage cloud infrastructure using code instead of manual steps in the console.
With Terraform, infrastructure can be:
Version controlled
Reused
Automatically created and destroyed

Why Use Terraform for EC2?
Removes manual errors
Makes infrastructure repeatable
Saves time
Helps in automation and DevOps workflows

Step 1: Create a Project Directory
mkdir terraform-ec2
cd terraform-ec2

Step 2: Configure the AWS Provider
provider.tf
provider "aws" {
  region = "ap-south-1"
}

Step 3: Define the EC2 Instance Resource
main.tf
resource "aws_instance" "my_ec2" {
  ami           = "ami-0f5ee92e2d63afc18"
  instance_type = "t2.micro"

  tags = {
    Name = "terraform-ec2"
  }
} 

Step 4: Initialize Terraform
terraform init

Step 5: Review the Execution Plan
terraform plan

Step 6: Apply the Terraform Configuration
terraform apply

Step 7: Verify the EC2 Instance
After successful execution:
Terraform displays the instance ID
EC2 instance appears in the AWS Console
Instance state shows Running

