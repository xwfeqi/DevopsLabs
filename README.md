# Lab 2: Launching an EC2 Instance Using AWS CLI

## Objective
Learn how to launch an **Amazon EC2** instance using **AWS CLI**, including setting up access keys, security groups, and automating instance configuration with `user-data`.

## Tasks
1. Create and configure an SSH key pair (`labkey`) for connecting to the instance.
2. Prepare a `userdata.txt` script for automatic instance setup.
3. Launch an EC2 instance using AWS CLI.
4. Verify that the instance runs and the `user-data` script executed correctly.

## Command to Launch the Instance
```bash
aws ec2 run-instances \
    --image-id ami-0360c520857e3138f \
    --count 1 \
    --instance-type t2.micro \
    --key-name labkey \
    --security-groups ec2defaultSG \
    --iam-instance-profile Name="ec2dafultrole" \
    --user-data file://"C:\Users\psycho\Desktop\Uni\3 course\devops\lab2\userdata.txt"
