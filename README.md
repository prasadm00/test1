
# CityPT Email Operations
## Getting Started



 # Real Cool Heading


### Prerequisites

- install AWS CDK `npm i -g aws-cdk`
- install the AWS CLI: https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html
- notate the name of your profile
  - for example, in my /.aws/credentials file, there is a profile named `cityptstaging`.
    When commands below reference `$PROFILE`, I indicate `--profile cityptstaging`
- clone the repo
- `npm install`
- copy `.env.example` to `.env`
  - add the citypt staging account number and region

#### AWS Objects
- AWS Pinpoint applicationId is created, app id value stored in resources/default.json
- Created application has sms and email channel enabled

### Deploying

`cdk deploy --profile $profile`

### User import
- Python script located at scripts/endpointImport.py
- Requires boto3 and aws credentials to be configured
- Usage: `python script.py sampleImport.csv`


### Testing

- run tests
`npm test`
- with code coverage
`npm test -- --coverage`

### Repo

- `/bin/citypt-email-operations.ts`
  - The main deployer for the CDK templates
- `/lib/citypt-email-operations-stack.ts`
  - The CDK stack definition
  - Edit this file to add new endpoints, layers, lambda functions, etc
- `src/citypt-email-operations-lambda/index.ts`
  - The lambda that receives a POST request from the API gateway and routes the payload
- `src/citypt-email-operations-lambda/marketingServiceApi.ts`
  - Module for AWS communication

### Monitoring

#### Health check endpoint

- Endpoint `/v1/ping` is responded to by /src/citypt-email-operations-lambda/index.ts

## Helpful Docs
- https://docs.aws.amazon.com/cdk/v2/guide/serverless_example.html
- https://docs.aws.amazon.com/cdk/v2/guide/hello_world.html
- https://github.com/bobbyhadz/aws-cdk-api-gateway-example
- https://github.com/bobbyhadz/aws-cdk-lambda-layers


 [Go to Real Cool Heading section](#real-cool-heading)





