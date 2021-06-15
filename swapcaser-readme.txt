# Swapcaser Deployment instructions

A SAM Lambda service (Python 3.6) that swaps case of text. Text becomes tEXT.

What is AWS SAM? https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/what-is-sam.html


To deploy, click on https://amzn.to/35jZJjH, tick all required capabilities and transforms at the bottom and click "Create Stack" 

TROUBLESHOOTING:
Swapcaser has some operational issues. Use X-ray & Cloudwatch logs to help fix any issues.
It uses an external service that can be a bit slow. They will upgrade the API Version at some point today, which will give a speed boost.

Cloudwatch Insights could also be useful using:

filter @type = "REPORT"
| stats avg(@duration), max(@duration), min(@duration) by bin(5m)

fields @timestamp, status, @message
| filter status not like /info/
| sort @timestamp desc
| limit 100

Lookup an X-ray request issue in Cloudwatch Insights:
fields @timestamp, @message
| filter @requestId like /REQUESTID/
