# S3 Static Website

## Step-by-Step :
1. Login to AWS console using you credential
2. On the console home, choose S3, and then click create bucket (the name must globally unique)
3. uncheck "Block Public Access" to allow public read access for the website hosting
4. you can enable or disable bucket versioning, add tag for the bucket, and encryption. it's all based on your preferences
5. click create bucket

6. go to your bucket, and click properties tab, and scroll down to "Static website hosting", enable it, so you can upload a simple index.html file
7. in the bucket permission tab, add "bucket policy" that grants public read access to the objects inb the bucket.
8. now you can access your S3 bucket on the browser.

##step-by-step using AWS CLI
1. AWWS Configure
2. create S3 bucket with this command (it follow the default region, when you run the aws configure

	//Execute the make bucket command: Use the aws s3 mb command followed by s3:// and your chosen bucket name
	aws s3 mb s3://your-unique-bucket-name

3. if you want to create the bucket on different region, use this command :

	//input your bucket name
	aws s3api create-bucket --bucket myawsbucket-yuma02 \

	//region for your bucket
	--region ap-southeast-1 \

	--create-bucket-configuration LocationConstraint=ap-southeast-1

4. to disable "block public access setting" use this command :
	
	aws s3api put-public-access-block --bucket myawsbucket-yuma02 --public-access-block-configuration "BlockPublicAcls=false,IgnorePublicAcls=false,BlockPublicPolicy=false,RestrictPublicBuckets=false"

5. enable static web hosting

	aws s3 website s3://myawsbucket-yuma02 --index-document index.html --error-document error.html

6. create a file bucket-policy.json and apply the policy with this command :
	
	aws s3api put-bucket-policy --bucket myawsbucket-yuma02 --policy file://bucket-policy.json

7. create a index.html and upload it to your bucket :

	aws s3 cp index.html s3://myawsbucket-yuma02/

8. now you can access your S3 bucket on the browser



## Screenshot
you can check the screenshot 'week-1/screenshots'
