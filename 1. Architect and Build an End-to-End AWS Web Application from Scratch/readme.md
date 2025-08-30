# Project Title : 
Architect and Build an End-to-End AWS Web Application from Scratch

# Project Description: 
This project is a simple web application that calculates an exponent — given a base number and an exponent, it returns the result (base^exponent). While the functionality is intentionally minimal, the purpose of the project is to demonstrate how different AWS services can be tied together into a complete, shareable, end-to-end application.

The app showcases how to:
- Host a static website with AWS Amplify,
- Expose a serverless API through API Gateway,
- Run backend logic with AWS Lambda (Python),
- Persist data in a DynamoDB NoSQL database, and
- Manage secure access with IAM permissions.

# Prerequisites
- AWS account with console access.
- Basic AWS knowledge (Lambda, API Gateway, DynamoDB).
- Text editor (VS Code, Notepad++).
- Python 3.9+ (for Lambda).
- Zip utility (to compress HTML for Amplify).

- [Project Title :](#project-title--)
- [Project Description:](#project-description-)
- [Prerequisites](#prerequisites)
- [Step-by-Step Guide:](#step-by-step-guide-)
  * [Create and host the web page:](#create-and-host-the-web-page-)
  * [Create the Lambda function:](#create-the-lambda-function-)
  * [Test the lambda function :](#test-the-lambda-function--)
  * [Create an API :](#create-an-api--)
  * [Create the DynamoDB table :](#create-the-dynamodb-table--)
  * [Policy implemention in the lambda function :](#policy-implemention-in-the-lambda-function--)
  * [Updating the Lambda function:](#updating-the-lambda-function-)
  * [Connecting the webpage with the API :](#connecting-the-webpage-with-the-api--)
  * [Observing the end result .](#observing-the-end-result-)

# Step-by-Step Guide: 

## Create and host the web page:

- Create a simple `"index.html"` file with the following code : 
![alt text](./Images/index.html.png)

- Zip the file :

![alt text](<Images/Screenshot 2025-08-29 012856.png>)

- Go to the `AWS Amplify` page and select `Deploy without Git` 

![alt text](<Images/Screenshot 2025-08-29 014945.png>)

- Provide the app name and the branch name 
![alt text](<Images/Screenshot 2025-08-29 015024.png>)

- Scroll down a little bit and upload the Zip file 
![alt text](<Images/Screenshot 2025-08-29 015049.png>)

- Wait for a moment , and we can see that the website is deployed. 
![alt text](<Images/Screenshot 2025-08-29 015127.png>)

- We can click on the link provided and it redierects us to the website . 

![alt text](<Images/Screenshot 2025-08-29 015153.png>)

![alt text](<Images/Screenshot 2025-08-29 015158.png>)

## Create the Lambda function: 

- Go to `AWS Lambda>Functions`

- Create a function : 

![alt text](<Images/Screenshot 2025-08-29 021521.png>)

- We can see that the function is created successfully . 

![alt text](<Images/Screenshot 2025-08-29 021634.png>)

- We now add the code from this file and deploy the function:

[lamba-function](lambda-func.py) 

## Test the lambda function : 

- Navigate to the `Test` tab : 

![alt text](<Images/Screenshot 2025-08-29 022756.png>)

- Create a new event and give it a name : 
![alt text](<Images/Screenshot 2025-08-29 022808.png>)

- Edit the `Event Json` : 

![alt text](<Images/Screenshot 2025-08-29 022929.png>)

- Hit `Test`

- We can check the result and see that it is as expected. 

![alt text](<Images/Screenshot 2025-08-29 023010.png>)

## Create an API : 

- Go to the `Amazon API gateway` 

- Select "Create a new API"

- We need to make a `Rest API` 

![alt text](<Images/Screenshot 2025-08-29 092910 1.png>)

- Select `New API` and provide the API's name 

![alt text](<Images/Screenshot 2025-08-29 092931.png>)

- Here we can see that the API is successfully completed. 

![alt text](<Images/Screenshot 2025-08-29 092945.png>)

- We need to create a method , in order to invoke the API. Select `Create method`
 
![alt text](<Images/Screenshot 2025-08-29 093002.png>)

- We shall select the method type as `POST` and select the integration type as `Lambda` , since we are going to invoke the lambda function. 

![alt text](<Images/Screenshot 2025-08-29 093027.png>)

- Select the desired lambda function

![alt text](<Images/Screenshot 2025-08-29 093034.png>)

-  We now need to enable CORS 

![alt text](<Images/Screenshot 2025-08-29 093104.png>)

- After all of the above processes , we hit save. 

![alt text](<Images/Screenshot 2025-08-29 093409.png>)

- After saving all the settings and configurations , we hit `Deploy API` and a pop up window opens up. 

![alt text](<Images/Screenshot 2025-08-29 093455.png>)

- We then select the Stage as `New Stage` and provide a stage name as we desire.

![alt text](<Images/Screenshot 2025-08-29 093508.png>)

- Now we shall get the following dashboard. 

![alt text](<Images/Screenshot 2025-08-29 093533.png>)

- We need to save the `Invoke URL` : 

![alt text](<Images/Screenshot 2025-08-29 093536.png>)

- Now for the testing part , we go to the POST tab and then select the `Test` tab. 

![alt text](<Images/Screenshot 2025-08-29 093643.png>)


- We type in the values and then hit "Test"

![alt text](<Images/Pasted image 20250829232939.png>)

- Here we can see the response 

![alt text](<Images/Pasted image 20250829233009.png>)

## Create the DynamoDB table : 

-  We shall be storing the response of the calculation in the database , hence we need to make a dynamodb database . 

-  We go to `DynamoDB > Tables > Create Table`  

![alt text](<Images/Screenshot 2025-08-29 234745.png>)

-  We are provided an interface to create the table . We input the name and the partition key.

![alt text](<Images/Screenshot 2025-08-29 234750.png>)

- We can observe that our table has been created.  

![alt text](<Images/Screenshot 2025-08-29 234826.png>)

- By clicking on the table , we can see the general information of the table . We need to note down the `ARN` of the table , as it will help later on in the formation of the policy. 

![alt text](<Images/Screenshot 2025-08-29 234841.png>)

## Policy implemention in the lambda function :

- In order to implement the policy in the lambda function , we need to navigate to the function's tab and then navigate to the `Configuration` tab. 

![alt text](<Images/Screenshot 2025-08-30 000255.png>)

![alt text](<Images/Screenshot 2025-08-30 000302.png>)

- Under the `Permissions` section , we can see that there is a `Role` ; the role name might be different for everyone. 

![alt text](<Images/Screenshot 2025-08-30 000439.png>)

- We go to the `Role` and we shall find a dashboard like below : 

![alt text](<Images/Screenshot 2025-08-30 000457.png>)

- We need to add a Inline Permission 

![alt text](<Images/Screenshot 2025-08-30 000500.png>)

- We navigate to the JSON policy navigator and input the following policy :

![alt text](<Images/Screenshot 2025-08-30 000810.png>)

The policy can be found here : [Lambda-policy](Lambda-func-policy.txt)

This policy effectively gives that function full CRUD access to the specified DynamoDB table.

- We then give the name of the policy and then create it : 

![alt text](<Images/Screenshot 2025-08-30 000827.png>)

![alt text](<Images/Screenshot 2025-08-30 000839.png>)

## Updating the Lambda function: 

- We now need to update the lambda function so that it will write to the dynamoDB table . 

-  We update the code : 

![alt text](<Images/Screenshot 2025-08-30 225516.png>)

- The code can be found here : [updated function](lambda-func-2.py)

- We know test the lambda function with the same variables ( u can chose ur own variables as well).

![alt text](<Images/Screenshot 2025-08-30 225707.png>)

- Here we can see that the test was successful : 

![alt text](<Images/Screenshot 2025-08-30 230518.png>)

- Now we need to check the Dynamodb to see if the changes was recorded or not : 

- Navigate to the table and then click `Explore Table Items`

![alt text](<Images/Screenshot 2025-08-30 230759.png>)

- Here we can see that the table was updated : 

![alt text](<Images/Screenshot 2025-08-30 230806.png>)

## Connecting the webpage with the API : 

- The current index.html is incapable of invoking the API , hence we need to update the code . 

- The updated code can be found here : [Updated index](index.html)

- I have put my ARN of the API , you need to put yours . 

- Zip the updated index.html and then reupload it to the Amplify . 

## Observing the end result . 

Here we can see that the alert is successfully popped up . 

![alt text](<Images/Screenshot 2025-08-30 234938.png>)