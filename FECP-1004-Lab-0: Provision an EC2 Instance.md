## Overview
In this lab, you will learn how to launch an EC2 instance within the public subnet of a default VPC and connect to it. Whether you're using Linux, macOS, or Windows, the guide provides tailored instructions, including using PuTTY for Windows users.


## 1. Launch an EC2 Instance

1-a. Open the **EC2 Dashboard**, navigate to **Instances**, and click **Launch Instance**.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-1.png)

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-2.png
)
1-b. Choose a name for the **EC2 instance**.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-3.png)

1-c. Select the **Amazon Linux 2023 AMI** and **t2.micro instance type** then scroll down below.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-4.png)

1-d. Choose a **key pair** from the dropdown menu. If no key pair is available, you can **create a new one**. If creating a new key pair, provide a name, download it, and store it securely.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-5.png)

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-6.png)

1-e. For the **network**, you may select the **VPC** that you have created from the previous lab. To do this, click on **Edit** then choose **your VPC** from the dropdown list. Also, select **Enable** for the **Auto-assign public IP**.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-7.png)

- Create a **new security group**, which you can rename. Enable the option to a**llow SSH traffic from anywhere** (port 22 open to 0.0.0.0/0), providing global SSH access (not recommended for production environments).

>Please note that this is not the best practice, we are only doing this for demonstration purposes.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-8.png)

1-f. Keep the default storage settings.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-9.png)

1-g. Review the configuration and click **Launch instance**.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-10.png)

**Congratulations!** Your EC2 instance is now running.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-11.png)

## 2. Connect to the EC2 Instance Using SSH (Linux/macOS)

2-a. Find your EC2 instance's **Public IPv4 Address.**
2-b. Open the **terminal** and navigate to the directory where your key pair is stored (e.g., ~/Downloads).

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-12.png)

2-c. Use the following command to connect:

`ssh -i <key-pair-name> ec2-user@<EC2-public-IP> `

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-13.png)

- Confirm the host authenticity when prompted by typing "**yes**".

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-14.png)

- If an **error** occurs regarding permissions, **proceed to the next step**.

2-d. Adjust the key permissions by running:

`chmod 400 <key-pair-name>`

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-15.png)

2-e. Try connecting again with the SSH command.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-16.png)

2-f. Once connected, update the instance packages by running:

`sudo yum update -y`

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-17.png)

## 3. Connect to the EC2 Instance Using PuTTY (Windows)

3-a. If PuTTY is not installed, **download** and **install** it from **putty.org**.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-18.png)

3-b. Select the right software for your device.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-19.png)

3-c. Convert the key pair from **PEM** to **PPK** using **PuTTYgen**:

- Open PuTTYgen from the Start menu.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-20.png)

- Click **Load**, navigate to your **PEM file**, and select it (ensure "All Files" is visible).

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-21.png)
![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-22.png)

- Save the private key as a PPK file.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-23.png)

- Click **OK**, then select the **Save private key** button. When prompted to save the key without a passphrase, click **Yes**.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-24.png)

- Navigate to the directory where you want to save your PPK file, enter a name for the file, and click **Save**.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-25.png)

3-d. Return to the Windows Start menu, search for **PuTTY**, and **launch** the application.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-26.png)

3-e. Type `ec2-user@<EC2 public IP>` into the **Host Name** field.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-27.png)

3-f. Expand the **SSH** section and click on **Auth** then select **Credentials**.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-28.png)

3-g. Browse for your saved **PPK file**. Click **Open**.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-29.png)

3-h. Click on **Accept** for when a PuTTY Security Alert prompt pops up.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-30.png)

**Congratulations!** You are now connected to your EC2 instance via SSH.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-31.png)

Run the command: `sudo yum update -y` to update software packages.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-32.png)

## 4. Connect to the EC2 Instance Using EC2 Instance Connect

4-a. Create a **new EC2 instance** by following steps 1-a to 1-f (except for selecting a key pair).
- In the **Configure Security Group** step, set a name and change the Source from **"Anywhere"** to **"My IP"** to restrict access to connections from your local machine.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-33.png)

4-b. You can now return to the **key pair login** step and select the option to **Proceed without a key pair**. Review then click on **Launch Instance**.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-34.png)

4-c. Open the **EC2 Management Console**, select your instance, and click **Connect**.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-35.png)

4-d. Ensure the **EC2 Instance Connect** option is selected, then click **Connect**.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-36.png)

- You will see an error message because the instance is restricted to connections from your specific IP address.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-37.png)

4-e. Close **Instance Connect**, return to the EC2 console, select your instance, and then choose **Actions > Security > Change Security Groups**.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-38.png)

4-f. Add the security group created earlier, **“EC2-demo-sg”** then remove the **"EC2-demo-sg2"** group, **Save** changes, and try connecting via **EC2 Instance Connect**.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-39.png)

- We have successfully established a connection to the EC2 instance using the EC2 Instance Connect service.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-40.png)

## 5. Connecting via Session Manager (Requires Additional Configuration):

5-a. Close the EC2 Instance Connect window and click **Connect** again. Select **Session Manager** this time. You'll encounter another error. 

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-41.png)

5-b. Go back to the **EC2 Management Console**, select the instance, and navigate to **Actions > Security > Modify IAM role**. 

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-42.png)

5-c. Create a new IAM role with the name **"EC2-SSM-Core-Role"** and attach the **AmazonSSMManagedInstanceCore** policy. 

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-43.png)

- On the next window, click on **Create role**. You will be redirected to another window. In here, select **AWS service**, **EC2**, and click on **Next**. 

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-44.png)

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-45.png)

- In the search bar, type **SSM** and select the **AmazonSSMManagedInstanceCore** policy. Then, click the **Next** button.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-46.png)

- Click **Next**, name the role **EC2-SSM-CoreRole**, add a description, and **create the role**. Close the IAM window.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-47.png)

- On the **Modify IAM Role** window, click the **refresh** button to update the list of available roles. Select the newly created **EC2-SSM-CoreRole** from the list and click the **Save** button.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-48.png)

5-d. Wait for a few minutes for the changes to take effect. Then, return to the **EC2 Management Console** and try connecting to your instance using **Session Manager**. Once the terminal session opens, execute the command **sudo su** to elevate your privileges to root.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session1/Lab1/image-49.png)

**Congratulations!** You've successfully completed the lab. Please copy the following JSON template into the left-side textbox:

**JSON**

Please copy the JSON to the textbox on the left side and fill in the required AWS resource details

```
{
   "ec2_instance_id": "",
   "region": ""
}
```

**Resource Cleanup**

Fill in the necessary AWS resource IDs. Once you've done that, don't forget to terminate all the instances and resources you created during this lab.
