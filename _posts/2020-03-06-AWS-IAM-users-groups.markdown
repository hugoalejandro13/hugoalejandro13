---
layout: "post"
title: "AWS: IAM Users & Groups"
---

AWS IAM (Identity and Access Management) is a secure way to manage access to different resources and services.

AWS's Console makes the set-up and utilziation of IAM easy.

First, we can begin by accessing the IAM section of the AWS Console
![image](/images/Capture1.PNG)

You will be brought to the IAM Dashboard. On the left-hand pane, select users.
![image](/images/Capture2.PNG)

In this example, there are three example users:
- user-1
- user-2
- user-3

Neither of these users currently belong to a Group. A Group allows you to easily specificy permissions to multiple users.

On the left-hand pane, select Groups.
![image](/images/Capture3.PNG)

We will be utilizing three example groups:
- EC2-Support
- EC2-Admin
- S3-Support

Each Group can be assigned IAM policies. Policies set what actions are allowed for specific AWS resources. There are two kinds of policies:

- Managed Policies : Either pre-determiend by AWS or by an admin)
- Inline Policies : Policies that are only assigned to one user or group

In this example:
- user-1 will be added to the S3-support Group
- user-2 will be added to the EC2-support Group
- user-3 will be added to the EC2-Admin Group

The S3-Support Group's Managed Policy will allow only group members ReadOnly access to the S3 Bucket.
If another user who is not a group member were to attempt to access the S3 Bucket, they would run into the following error.
![image](/images/user2-s3fail.PNG)

The EC2-Support Group's Managed Policy will allow only group members to have Read-Only acces to the EC2 instances. If a group member were to attempt any actions outside their permissions, such as stopping the instance, they'd run into the following error.
![image](/images/user2-ec2stopfail.PNG) 

The EC2-Admin Group does not have a Managed Policy. Instead, it utilizes an Inline policy, which are only assigned to one user or group. The Inline Policy allows group members to view, start and stop EC2 instances. Unlike group members of EC2-Support, if a user of EC2-Admin were to attempt to stop an EC2 instance, they would be able to.
![image](/images/user3-ec2stop.PNG)

That's it! You should have a basic understanding of AWS IAM Users, Groups and Policies!
