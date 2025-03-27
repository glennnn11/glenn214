# Assignment 2.14

# SNS, DLQ, and CloudWatch

## 1. Does SNS guarantee exactly once delivery to subscribers?
No, Amazon SNS does not guarantee exactly once delivery. It provides at least once delivery, meaning a message may be delivered more than once to the subscribers in certain cases, such as network issues or retries.

## 2. What is the purpose of the Dead-letter Queue (DLQ)?
A Dead-letter Queue (DLQ) is used to capture messages that fail to be processed successfully after a set number of attempts. It helps in analyzing and troubleshooting message delivery failures in services like SQS, SNS, and EventBridge.

## 3. How would you enable a notification to your email when messages are added to the DLQ?
To receive an email notification when messages are added to a DLQ:
1. Create an SNS topic and subscribe your email.
2. Set up a CloudWatch Alarm to monitor the `ApproximateNumberOfMessagesVisible` metric for the DLQ.
3. Configure the CloudWatch Alarm to send an SNS notification when messages are added to the DLQ.
