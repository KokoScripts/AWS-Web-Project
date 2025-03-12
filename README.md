# AWS-Web-Project
This project demonstrates how to design and build a simple web application on AWS using five key services: Amplify, Lambda, IAM, API Gateway, and DynamoDB.

I followed the [Tutorial by Tiny Tech Tutorials](https://youtu.be/7m_q1ldzw0U?si=-u2LWjtARnRJilov) YouTube tutorial to complete this step-by-step guide on my AWS account.

### Requirements
- AWS account
- Text editor (e.g., Notepad, VSCode)
- Basic AWS knowledge
  
### Level
Beginner 

#### Step One - Create the HTML
1. Create a new file named index.html.
2. Open it in your preferred text editor.
3. Copy and paste the [HTML content](https://github.com/KokoScripts/AWS-Web-Project/blob/main/index.html) for this project into the file and save it.
4. Compress the file into a .zip format (e.g., index.zip).

#### Step Two - Deploy the file on AWS Amplify
1. Sign into AWS account and navigate to Amplify.
   ![Image](https://github.com/user-attachments/assets/bbd22c6d-3b29-4403-8313-8c34d7d14ae9)
2. Click  **Deploy an app**.
   ![Image](https://github.com/user-attachments/assets/ff22f309-c470-4eb6-86d2-8dd351964300)
3. Select **Deploy without Git**.
   ![Image](https://github.com/user-attachments/assets/10f68086-8032-4a06-8310-39731b860ce0)
4. Scroll down and click **Next**
5.Upload the index.zip file created in Step 1
   ![Image](https://github.com/user-attachments/assets/5d2e92ec-e74f-490a-a8aa-5b00239ff917)
6.Change the **App name** (optional) and update **Branch name** from "staging" to "Dev".
   ![Image](https://github.com/user-attachments/assets/c9e5f607-5b8d-4645-b274-35b948d44ac5)
7. Scroll down and click **Save and deploy**
8. Open the generated link in a new tab to test your deployed app.
   ![Image](https://github.com/user-attachments/assets/64027ada-9773-4304-afaf-4a491715eb01) 

#### Step Three - Automate calculation with AWS Lambda  
1. **Duplicate the AWS Console tab** and open the new tab.  
2. Navigate to **AWS Lambda**.  
3. Click **Create a function**.  
4. Select **Author from scratch**.  
5. Enter your preferred **Function name**.  
6. Choose **Python 3.9** for **Runtime**.  
7. Leave all other settings at default.  
8. Click **Create function** at the lower-right corner.
9. Scroll down to the **Code** tab.
10. Replace the default code with the code [here](https://github.com/KokoScripts/AWS-Web-Project/blob/main/Original-Lambda.txt)
11. Ctrl + S to save
12. Click **Deploy**. The prompt *Successfully updated the function (App Name).* should appear.
13. Click **Test**. Then Click **Create new test event**
14. In the test event dashboard that opos-up on the right, enter your preferred Event name.
15. Keep it in Private
16. Remove Key3 and Value3.
17. Replace value1 and value2 with numbers










   
