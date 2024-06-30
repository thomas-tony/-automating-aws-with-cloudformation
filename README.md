# Automating AWS with CloudFormation

This project provides a step-by-step guide to automate AWS infrastructure using CloudFormation.

## Getting Started with AWS CloudFormation

### Step 1: Creating a CloudFormation Template

The first step in using CloudFormation is to create a template that describes the AWS resources you want to provision. Templates are written in JSON or YAML and include several key sections, such as Resources, Parameters, and Outputs.

Here’s a simple example of a YAML template that provisions an EC2 instance:

```yaml
AWSTemplateFormatVersion: '2010-09-09'
Description: Simple EC2 instance
Resources:
  MyEC2Instance:
    Type: 'AWS::EC2::Instance'
    Properties:
      InstanceType: t2.micro
      ImageId: ami-0c55b159cbfafe1f0
      KeyName: my-key-pair
```

- Replace my-static-website with your bucket name.
- Click “Save changes.”

### Step 2: Creating a Stack
Once you have your template ready, you can use it to create a CloudFormation stack. A stack is a collection of AWS resources defined by the template.

You can create a stack using the AWS Management Console, AWS CLI, or AWS SDKs. Here’s how to create a stack using the AWS CLI:

```sh
   aws cloudformation create-stack --stack-name MyStack --template-body file://templates/ec2-instance.yaml


## Step 3: Monitoring and Managing Stacks
After creating a stack, you can monitor its progress and manage its resources using the AWS Management Console or AWS CLI. CloudFormation provides detailed information about the stack’s status and events, helping you track the provisioning process.

To check the status of a stack using the AWS CLI:

```sh
   aws cloudformation describe-stacks --stack-name MyStack

## Step 4: Updating a Stack
When you need to make changes to your infrastructure, you can update your CloudFormation template and apply the changes to the existing stack. CloudFormation will determine the necessary updates and apply them in a controlled manner.

To update a stack using the AWS CLI:

```sh
   aws cloudformation update-stack --stack-name MyStack --template-body file://templates/updated-ec2-instance.yaml

## Step 5: Deleting a Stack
If you no longer need the resources provisioned by a stack, you can delete the stack, and CloudFormation will automatically clean up all the associated resources.

To delete a stack using the AWS CLI:

```sh
   aws cloudformation delete-stack --stack-name MyStack

## Additional Resources

For a detailed step-by-step guide, please refer to [my blog post](https://tonythomas.in/automating-aws-with-cloudformation/).


