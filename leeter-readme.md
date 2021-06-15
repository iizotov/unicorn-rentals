# Leeter Deployment instructions

An Elastic Beanstalk service that converts text to l33tspeak. Example becomes 3x4mpl3.

This microservice also gets details about your team at runtime from SSM Parameter Store, for signing its messages. 
The elastic beanstalk source package is leeter-elastic-beanstalk-python36.zip

* Go to the [AWS Elastic Beanstalk Console](https://ap-southeast-2.console.aws.amazon.com/elasticbeanstalk/home?region=ap-southeast-2#/gettingStarted), and create an application named `leeter` on Python 3.6 platform using `https://unicorn-rentals-561287.s3.ap-southeast-2.amazonaws.com/leeter-elastic-beanstalk-python36.zip` as the source code S3 URL

Troubleshooting:

Troubleshoot with Elastic Beanstalk logging. Optionally configure for Cloudwatch Logs and Amazon Xray.
