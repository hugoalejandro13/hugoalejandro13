---
layout: "post"
title: "Friday The 13th, Perfect Day to learn about EBS"
---

It's Friday, March the 13th and I cannot think of a better time to learn about AWS Elastic Block Store!

Amazon Elastic Block Store (EBS) provide independent scalable, adaptable block storage for EC2 instances. EBS volume types are available in either SSD backed volume types or HDD backed volumes types, depending on need.

Attaching an EBS Volume to an EC2 Instance

Navigate to the EC2 section under the Services Menu in the AWS Management console
![image](/hugoalejandro13/images/blog6/Capture.PNG)

Click on Volumes along the left-hand navigation pane.
![image](/hugoalejandro13/images/blog6/Capture1.PNG)

Click on the Create Volume button, after which you'll have the following screen. In this case we will be creating a 1 Gb General Purpose SSD names My Volume. Click Create Volume, followed by Close.
![image](/hugoalejandro13/images/blog6/Capture2.PNG)

Next, we'll attach the Volume to our existing EC2 instance.
![image](/hugoalejandro13/images/blog6/Capture3.PNG)

Next, we'll connect to our EC2 instane through SSH. In this example I am utilizing PuTTY on Windows.

Run the following command to list attached storage to the EC2:

df -h
![image](/hugoalejandro13/images/blog6/Capture4.PNG)

Create an ext3 file system on the newly attached volume with the following:
sudo mkfs -t ext3 /dev/sdf
![image](/hugoalejandro13/images/blog6/Capture5.PNG)

Run the following to create a directory and mount the new storage volume:

sudo mkdir /mnt/data-store
sudo mount /dev/sdf /mnt/data-store
![image](/hugoalejandro13/images/blog6/Capture6.PNG)

Creating an EBS Snapshot
Navigate to the Volumes menu within the AWS Management Console. Select the previously created volume and select "Create Snapshot" from the Actions menu.
![image](/hugoalejandro13/images/blog6/Capture9.PNG)

Enter the following information on the following screen.
![image](/hugoalejandro13/images/blog6/Capture10.PNG)

Restoring an EBS screenshot

You can utilize an EBS screenshot as a recovery point. In order to restore from a snapshot, Navigate to the Snapshots menu on the left-hand pannel. Select the snapshot you'd like to restore. Click on the Actions menu and select Create Volume.
![image](/hugoalejandro13/images/blog6/Capture11.PNG)

Enter the following information on the next screen.
![image](/hugoalejandro13/images/blog6/Capture12.PNG)

And that's it! You've now succesfully taken snapshots of EBS volumes, as well as restored a volume from a snapshot!
