# AWS CDK Hack for AWS Academy Learner Lab

AWS Academy Learner Lab disallows everyone creates any IAM resources and most of the AWS services do not work or need to do it in a hacking way!
You cannot run AWS CDK in a standard way as it always follows the AWS best practise while AWS Academy Learner is targeting to train students ignoring IAM and a hackers loves this!

There are 2 tricks: 
1. Use customized CDK bootstrap
2. Customized Stack synthesizers that uses LabRole for eveything!

## Use customized CDK bootstrap
You have to use the customized bootstrap which removed all IAM resources.
```cdk bootstrap --template bootstrap-template.yaml```
This template is developed under CDK 2.23.0 (build 50444aa).
However, you can rebuild it easily by following 
https://docs.aws.amazon.com/cdk/v2/guide/bootstrapping.html#bootstrapping-customizing


/aws-cdk-hack-for-aws-academy-learner-lab/bin/aws-cdk-hack-for-aws-academy-learner-lab.ts

This is a project template for CDK development with TypeScript.

The `cdk.json` file tells the CDK Toolkit how to execute your app.

## Useful commands

* `npm run build`   compile typescript to js
* `npm run watch`   watch for changes and compile
* `npm run test`    perform the jest unit tests
* `cdk deploy`      deploy this stack to your default AWS account/region
* `cdk diff`        compare deployed stack with current state
* `cdk synth`       emits the synthesized CloudFormation template
