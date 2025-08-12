## EC2 Deployment

## Step-by-Step :
1. Login to AWS console using you credential
2. On the console home, choose EC2, and then launch instance
3. You can fill in the name for your instance, choose the AMI (OS Images), in this guide I use Amazon Linux
4. For instance type I choose t2.micro
5. Create a new key pair if it is the first time you try to create an EC2
6. COnfigure Security Group, check allow SSH and allow HTTP
7. launch instance.

## EC2 Deployment using AWS CLI
1. login to AWS console
2. create EC2 instance with this command

    aws ec2 run-instances \

    --image-id ami-0061376a80017c383 \
    //image id for Amazon Linux

    --instance-type t2.micro \
    //the desired instance type (e.g., t2,micro, m5.large)

    --key-name aug_key\
    //keypair name, same as keypair that you already have before

    --security-group-ids sg-0cb7bce85fe8d3b5e \
    //security group id, same as security that you already have before

    --subnet-id subnet-0f7b102a788e00e6b \
    //the ID of the subnet within your VPC where you want to launch the instance

    --count 1 \
    //the amount of instance that you will create, it's up to you


3. enter, and your instance will be launch.

## Screenshot
you can check the screenshot 'week-1/screenshots'
