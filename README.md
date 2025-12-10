# Serverless Event-Driven-Workflow with AWS Glue and Amazon Event Bridge
Event Driven Workflow using AWS Glue and Amazon Event Bridge

## Project Overview
This project shows how to configure AWS Glue workflows to run based on real-time events. The benifits for these workflows are there is no need to set schedules or build complex solutions to trigger jobs based on events; We can hire AWS Glue for event-driven workflows. This project is designed using references from AWS Blogs.

## 🛠Technologies Used
- **AWS Services:** S3, CloudTrail, Event Bridge, Glue Wokrflow, Lambda, IAM, Cloud Formation, AWS CLI
- **Python Libraries:** Boto3, Pandas, PyArrow

## Project Architecture
![Architecture](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/07/13/glue_event_driven_workflow.png)

## Steps for solution:
- Create AWS Glue workflow with starting trigger of EVENT type and configure the batch size on trigger to five and batch window to be 900.
- Configure Amazon S3 to log data events, such as PutObject API calls to CloudTrail.
- Create a rule in EventBridge to forward the PutObject API events to AWS Glue when they are emitted by CloudTrail.
- Add an AWS Glue event-driven workflow as a target to the EventBridge rule.
- To start the workflow, upload files to the S3 bucket. Remember to have minimum of five files before the workflow is triggered.

## Solution Process:
- Trigger the AWS Glue workflow by uploading files to Amazon S3
- Verify the AWS Glue workflow in triggered successfully
- Verify the metrics for the EventBridge rule( Use Amazon CloudWatch metrics to validate the events sent to the AWS Glue workflow)
  
## ETL Workflow Process:
- Extract: Sorting data in S3 that comes from end API, and these got captured by AWS Cloud Trail. RUles in the EVnt Bridge to forward PutObject API events to AWS Glue when emitted by CloudTrail.
- Transform: The eventbased workflow is triggered to AWS Glue.
- Load: Finally, After the transformation files are uploaded into S3 Bucket.

## Solution Deployment:
- To quick start the solution, The AWS CLoudFormation stack is used to build all required resources

## Clean up:
- Final step, Clean up the resources, The AWS CloudFormation stack to remove any resources created as part of this walkthrough.
## Conclusion:
- AWS Glue event-driven workflow can be built easily for event driven ETL pipelines which respond in near-real time, delivering fresh data to business users.

## Main Source of this project: 
https://aws.amazon.com/blogs/big-data/build-a-serverless-event-driven-workflow-with-aws-glue-and-amazon-eventbridge/


