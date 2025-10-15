This project demonstrates a simple and secure REST API using AWS CloudFormation, Lambda, and API Gateway.
It returns a list of books and requires a student ID–based API key for access.

This template can be used to create an AWS CloudFormation Stack consisting of a Lambda function which is invoked via API Gateway.

To create and deploy a Stack in US East region, issue the following command using AWS CLI tool:
aws cloudformation deploy --template-file booklist-lambda-restapi.yaml --stack-name BookListStack --capabilities CAPABILITY_NAMED_IAM --parameter-overrides StudentId=STU123456 StageName=dev --region us-east-1

After successful stack creation, get the API URL by issuing the following command using AWS CLI tool:
aws cloudformation describe-stacks --stack-name BookListStack --region us-east-1 --query "Stacks[0].Outputs[?OutputKey=='InvokeUrl'].OutputValue" --output text



