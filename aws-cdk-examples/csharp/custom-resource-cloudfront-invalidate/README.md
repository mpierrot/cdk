# Custom Resource CloudFront Invalidate

This example uses an [AwsCustomResource](https://docs.aws.amazon.com/cdk/api/v2/dotnet/api/Amazon.CDK.CustomResources.AwsCustomResource.html) to produce an invalidation on an Amazon CloudFront Distribution. A CloudFront Invalidation wipes away the cached content so that new changes in the distribution's origin can be seen immediately.

The `AwsCustomResource` CDK construct is an [L3 Construct](https://docs.aws.amazon.com/prescriptive-guidance/latest/aws-cdk-layers/layer-3.html) that can be used to create an AWS CloudFormation Custom Resource without having to directly create the AWS Lambda Function to support it.

An `AwsCustomResource` is appropriate to use when you have exactly one AWS SDK call to make per [stack task](https://docs.aws.amazon.com/vsts/latest/userguide/cloudformation-create-update.html): `onCreate`, `onUpdate`, and `onDelete`.

## Build

To build this app, you need to be in this example's root folder. Then run the following:

```bash
npm install -g aws-cdk
dotnet build src
```

This will install the necessary CDK, then this example's dependencies, and then build your csharp files and your CloudFormation template.

## Deploy

Run `cdk deploy CustomResourceCloudFrontInvalidateStack`. This will deploy / redeploy your Stack to your AWS Account.

After the deployment you will see the API's URL, which represents the url you can then use.


## Synthesize Cloudformation Template

To see the Cloudformation template generated by the CDK, run `cdk synth CustomResourceCloudFrontInvalidateStack`, then check the output file in the "cdk.out" directory.