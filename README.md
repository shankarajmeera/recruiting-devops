# DevOps Recruiting Exercise

## Overview

Here at [Foreground](https://foreground.co), we prefer to understand a candidate's technical experience and analysis skills before proceeding with portions of our recruiting process. We believe that the exercise below will illustrate a candidate's approach to working with technologies and methodologies that may be commonly used in our teams at Foreground.

## Guidelines

* This exercise should not take you more than one to two hours to complete. If
  your solution is taking longer, that's okay—be honest and let us know how long
  it took and why you think it took that long.
* Be as thorough as you wish.
* All exercises are to be performed as if you were on the job.
* We use [terraform](https://www.terraform.io/) to manage our cloud infrastructure on AWS. Provide your exercise files as valid terraform code.
* We'd expect to see the specific resources defined in the `terraform/development/devops-recruiting-exercise` directory and any shared modules in `terraform/modules` directory, but we are open to other approaches if you can justify your reasoning.
* You are free to use whatever development environment you wish. We use [Visual Studio Code](https://code.visualstudio.com/) with the official Hashicorp Terraform extension to help with formatting.
* You may submit your response by forking this repository and opening a pull request. You can then send that link to the pull request to the recruiter you are working with.

There are no right or wrong answers. We are deliberately offering creative freedom and interpretation to all candidates who are completing this exercise. You would receive similar tasks on the job and would be given similar latitude with how you approach the problem and deliver business insights.

## Instructions
- Use this repository to kickstart your project.
- Fork or download this repository.
- [KISS](https://en.wikipedia.org/wiki/KISS_principle).
- Install the terraform CLI: [Instructions](https://learn.hashicorp.com/tutorials/terraform/install-cli)
- Use the terraform CLI to test your changes using `terraform plan`
- (Optional) You can use the [AWS Free Tier](https://aws.amazon.com/free) to create the resources in this exercise if you wish. Make sure you remain within the free tier limits so that you are not charged. _Foreground is not responsible for any charges you may incur doing this exercise_.
- Complete the following steps in your fork and open a pull request.

## STEP 1: VPC and Networking

**Goal:** Create a VPC and the associated networking to be able to launch an EC2 instance

### Requirements

- We only need 1 availability zone.
- No NATs are required.
- All instances launched in this VPC will be given an auto-assigned public IP address.

## STEP 2: EC2 instance

**Goal:** Launch an EC2 instance in the VPC created in the previous step.

### Requirements
- Use the previously created VPC outputs as inputs to the EC2 resource.
- Launch the default Amazon Linux 2 AMI for whatever region we set up.

## STEP 3: S3 setup

**Goal:** Create an S3 bucket and only allow the EC2 instance created in the previous step to read and write (but not delete or list) information to that bucket.

### Requirements
- The S3 bucket is setup with the relevant properties and permissions.
- Create an IAM role for the EC2 instance created in the previous step.
- Assign an instance role to that instance and assure that role has permissions to read and write (only) to that s3 bucket.

## STEP 4: Optional / Bonus
- Show a working example by hooking all this up to a [Terraform Cloud account](https://app.terraform.io/signup/account) and a [Amazon Web Services account](https://aws.amazon.com/free). Both providers have free tiers.
- Consider scenarios where we may wish to deploy this infrastructure across different environments (i.e. stage, test, production) and what approach you might take to enable this.
