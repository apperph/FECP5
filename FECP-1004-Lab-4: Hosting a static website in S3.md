## Overview

In this lab, you will configure **Amazon S3** to host a static website and use **Amazon CloudFront** to cache and improve performance.

---

## 1. Create an S3 Bucket

### 1-a. Create a Bucket
Log in to your **AWS account**, navigate to the **S3 console**, and click on **Create Bucket**.

![Step 1-a](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-1.png)

### 1-b. Configure the Bucket
- Set a name for your **S3 bucket**  
- **Uncheck** the option to **Block all public access**  
- Under **Object Ownership**, select **ACLs enabled**  
- Click **Create Bucket**

![Step 1-b-1](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-2.png)  
![Step 1-b-2](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-3.png)  
![Step 1-b-3](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-4.png)  
![Step 1-b-4](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-5.png)

---

## 2. Set Up Static Website Hosting

### 2-a. Download Website Files
Download and extract the static website files from:  
 [static_website.zip](https://camp-labs.s3-ap-southeast-1.amazonaws.com/static_website.zip)

You will get:
- `index.html`
- `badge-camp.png`

![Download files](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-6.png)

### 2-b. Upload Files to S3
Navigate to your **S3 bucket** and click on **Upload**.

![Upload](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-7.png)

### 2-c. Upload `index.html` and `badge-camp.png`

![Upload files](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-8.png)

### 2-d. Confirm Upload Status

![Upload status](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-9.png)

---

### 2-e. Enable Static Website Hosting
- Go to your bucket's **Properties** tab  
- Scroll to **Static website hosting** and click **Edit**

![Properties](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-10.png)  
![Edit hosting](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-11.png)

### 2-f. Configure Hosting Settings
- Enable **Static Website Hosting**  
- Set `index.html` as the index document  
- Optionally set `error.html` as the error document

![Hosting settings](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-12.png)

### 2-g. Copy the Static Website URL  
Copy the **Endpoint URL** provided.

![Copy URL](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-13.png)

### 2-h. Try Accessing the Website  
At this point, the website **won’t be accessible** yet as the files are still private.

![Blocked access](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-14.png)

---

### 2-i. Make Files Public
- Go back to your **S3 bucket**
- Select both uploaded files
- Click **Actions > Make public**

![Make public](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-15.png)

#### If the option is disabled:
1. Go to **Permissions > Object Ownership**
2. Select **ACLs enabled**
3. Confirm changes

![Fix ACLs 1](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-16.png)  
![Fix ACLs 2](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-17.png)  
![Make public again](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-18.png)

---

### 2-j. Access the Website
Now return to your browser and enter the static website URL.

![Website success](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-19.png)

---

## Success!
You have successfully hosted a **static website** on an **S3 bucket**!

---

## JSON Submission

Please copy the JSON below, fill in your AWS resource details, and submit it in the provided textbox:

```json
{
  "s3_bucket_arn": "",
  "s3_web_endpoint": ""
}
