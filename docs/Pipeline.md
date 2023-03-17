# CI/CD Pipeline

The pipeline is employed using [CircleCI](https://circleci.com/). There are three steps to the overall pipeline:
1. Build
2. Hold
3. Deploy

![Pipeline Overview](../screenshots/Pipeline.png?raw=true)

## Build

The build step is used to ensure the application can be built properly and has no errors. For both the frontend and backend applications, it installs the necessary dependencies, runs the linter, and then builds the applications.

![Build Step](../screenshots/BuildStep.png?raw=true)

## Hold

The hold step is a manual step that requires an approval before moving onto the deploy. A user must click the "approve" button in order for the pipeline to continue. This can be seen in the pipeline overview above as there are no details to show for the step.

## Deploy

The deploy step is used to deploy the application. For both the frontend and backend applications, it installs the necessary dependencies, builds the applications, and then deploys them. The frontend app is deployed to S3 via the [AWS CLI](https://aws.amazon.com/cli/). The backend app is deployed to Elastic Beanstalk via [its CLI](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3.html).

![Deploy Step](../screenshots/DeployStep.png?raw=true)