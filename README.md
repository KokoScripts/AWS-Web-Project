# AWS-Web-Project
This project demonstrates how to design and build a simple web application on AWS using five key services: Amplify, Lambda, IAM, API Gateway, and DynamoDB.


### Prerequisite
- AWS account
- Text editor (e.g., Notepad, VSCode)
- Basic AWS knowledge
  
### Level
Beginner 

#### Step One - Create the HTML file
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
5. Upload the index.zip file created in Step 1
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
10. Replace the default code with the code from [this link](https://github.com/KokoScripts/AWS-Web-Project/blob/main/Original-Lambda.txt).
11. Press **Ctrl + S** to save.
12. Click **Deploy**. A confirmation message should appear: *Successfully updated the function (App Name).*
13. Click **Test**, then select **Create new test event**.
14. In the test event panel on the right, enter an **Event name** of your choice.
15. Keep the event **Private**.
16. Delete **Key3** and **Value3**.
17. Replace **Value1** and **Value2** with numbers (remove quotation marks and the last comma).
18. Replace **Key1** with *base* and **Key2** with *exponent* respectively.
19. Invoke the test. (A successfully response will have a statuscode:200 and the result of the math calculation).
20. Scroll up and click **Save**.
    
#### Step Four - Invoke Lambda Function with Amazon API Gateway
1. **Duplicate** the AWS Console tab and navigate to **API Gateway**.  
2. Scroll down and click **Build** under **REST API**.  
3. Enter an **API name** and leave all other settings as default.  
4. Click **Create API**.  
5. Click **Create Method**.  
6. Select **POST** as the **Method type**.  
7. Choose **Lambda Function** as the **Integration type**.  
8. Enter your **Lambda function name**.  
9. Scroll down and click **Create Method**.  
10. On the new page, click **Deploy API**.  
11. Select **New Stage**, enter a **Stage name**, and deploy.  
12. Scroll down, copy the **Invoke URL**, and store it safely.  
13. Go to the **Resources** section and click **Enable CORS**.  
    - Select **Default 4XX, 5XX, and POST**.  
    - Click **Save**.  

 *By default, browsers enforce the Same-Origin Policy, which blocks requests from different domains for security reasons.
    Enabling CORS lets your API explicitly permit requests from specific domains, headers, and methods.*

#### Step Five - Store and Return data using Amazon DynamoDB
1. Navigate to Amazon DynamoDB
2. Click on **Create table**
3. Enter your preferred database name.
4. Enter ID as partition key.
5. Leave everyother option at default.
6. Scroll down and Click **Create table**
7. Click on the table link to open.
8. Expand the additional info section. Copy the ARN and store safely in a notepad.

### Step Six - Update the Lamba function permissions with AWS IAM
1. Go back to your Lambda function page
2. Scroll down and open the **Configuration** tab and select **Permissions**
3. Click the link below **Role name**. This will redirect to IAM dashboard
4. Click **Add permissions**. Select **Create inline policy**
5. Select the JSON tab.
6. Replace the code there with the one [here](https://github.com/KokoScripts/AWS-Web-Project/blob/main/Execution-Role-Policy.json)
7. Enter your DynamoDB ARN in line 15 of the code.
8. Click **Next**. Enter policy name and create policy.
9. Go back to your previous Lambda Function code and Replace it with this [one](https://github.com/KokoScripts/AWS-Web-Project/blob/main/PowerOfMathFunction%20-%20Lambda-FINAL.txt).
10. Replace table name in the code (line 14) with your table name.
11. Ctrl + S to save. Click **Deploy**
12. Run a test one more time to be sure your code works.
13. Refer to this [file](https://github.com/KokoScripts/AWS-Web-Project/blob/main/Test-error-troubleshoot) if the test fails.
   
### Step 7 - Putting them all together
1. Update the previous HTML code in your text editor to this [one](https://github.com/KokoScripts/AWS-Web-Project/blob/main/Final-index.html) Replace line 60 with your API Gateway URl
2. Compress the file again.
3. 










   
