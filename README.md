# AWS CloudFormation

AWS CLI: https://docs.aws.amazon.com/cli/latest/reference/cloudformation/index.html


## Command to create the stack

```bash
aws cloudformation create-stack --stack-name teststack01 --template-body file://csye6225-infra.yaml --parameters ParameterKey=VpcCidrBlock,ParameterValue=10.0.0.0/16 ParameterKey=SubnetCidrBlock1,ParameterValue=10.0.1.0/24 ParameterKey=SubnetCidrBlock2,ParameterValue=10.0.2.0/24 ParameterKey=SubnetCidrBlock3,ParameterValue=10.0.3.0/24
````

## Validate Template

```bash
aws cloudformation validate-template --template-body file://csye6225-infra.yaml
```

## Update Stack

```bash
aws cloudformation update-stack --stack-name myvpc --template-body file://csye6225-infra.yaml
```

## Delete Stack

```bash
aws cloudformation delete-stack --stack-name <stack-name>
```

# AWS CLI Setup

```bash
aws configure set region <us-west-2> --profile <Profile_name>
```

```bash
aws configure get region --profile <Profile_name>
```

```bash
export AWS_PROFILE=admin-dev or produser
```

```bash
echo $AWS_PROFILE
```

# Import SSL certificate to ACM 
```bash
aws acm import-certificate --certificate fileb://Certificate.pem
--certificate-chain fileb://CertificateChain.pem
--private-key fileb://PrivateKey.pem
```

# Command to create stack
```bash
aws cloudformation deploy --profile prodUser --template-file csye6225_infra_2.yaml  --parameter-overrides KeyName=prodKey ImageId=ami-0be5bf228a27b5c49 --stack-name teststack33 --region=us-east-1 --capabilities CAPABILITY_NAMED_IAM
```