**Carry out all solutions for better results**

### Solution one - Updating database name

Ensure that the database name in line 14 of the updated policy should match your actual database name.

### Solution 2 - Fixing IAM Permissions for Lambda and DynamoDB

#### Attach the Correct Permissions to the IAM Role
Your Lambda function runs with the IAM role **NewApp-role-borl3ai2**, but it does not have the required permissions to write to DynamoDB.

1. Go to the AWS IAM Console
2. Navigate to **IAM > Roles**.
3. Search for **NewApp-role-borl3ai2**.
4. Click on the role (**NewApp-role-borl3ai2**).
5. Go to the **Permissions** tab.
6. Click **Add permission**. Select **create inline policy**
7.  Select the JSON tab and enter the code below:

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "dynamodb:PutItem"
            ],
            "Resource": "arn:aws:dynamodb:eu-north-1:842675996729:table/**<YOUR DATABASE NAME>**"
        }
    ]
}
```

8. Click **Next**. 
9. Give the policy a name. Then click **Create Policy**

#### 2.1 Verify IAM Trust Relationship
Ensure that the Lambda function is allowed to assume the role.

1. In the **IAM Console**, go to **Roles > NewApp-role-borl3ai2**.
2. Click the **Trust relationships** tab.
3. Ensure it has the following policy:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "lambda.amazonaws.com"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}
```
Go back to Lambda and run the test again. If successfull, it should return statuscode:200 and the results of the calculation.
