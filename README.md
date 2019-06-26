# Elastic Beanstalk with Flask

This repository was made by following the article [Deploying a Flask Application to AWS Elastic Beanstalk](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/create-deploy-python-flask.html) written by AWS.

## Setup your virtualenv, activate it, install requirements

```bash
$ virtualenv venv -p python3
$ . venv/bin/activate
$ pip install -r requirements.txt
```

## AWS/EB Command Line Setup

The [EB CLI](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3.html) is a command line interface for Elastic Beanstalk that provides interactive commands that simplify creating, updating and monitoring environments from a local repository.

To use AWS Elastic Beanstalk you must have:

* An aws account with an *aws_access_key_id* and *aws_access_key_id*
* Your account must be privileged enough to use the Elastic Beanstalk service
* You must have installed and configured the [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-install.html)
* You must have installed and configured the [AWS Elastic Beanstalk CLI](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3.html) 

If you're using multiple AWS accounts it's helpful to manage them with [named profiles](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-profiles.html). 

Verify it's working with:

```bash
$ aws sts get-caller-identity
{
    "Account": "<your_account_id>",
    "UserId": "<your_user_id>",
    "Arn": "<your_arn>"
}
```

## Create your Elastic Beanstalk environment

In the AWS article initialize the Elastic Beanstalk environment with `eb init` to create the *.elasticbeanstalk* directory that is already commited to this repository. Afterwards you can create your beanstalk environment and then deploy it. 

```bash
$ eb create flask-env
$ eb open
```

When you're done terminate it with `eb terminate`.