# Check AWS access keys

Generate a report, displaying each user and number of access keys they have:

* active keys (created in the last 60 days)
* obsolete keys (older than 60 days)
* inactive keys

The goal of this report is to monitor, if users are rotating their keys in a timely manner.

For this report to work, the following policy must be in place:

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "VisualEditor0",
            "Effect": "Allow",
            "Action": [
                "iam:ListUsers",
                "iam:GetUser",
                "iam:ListAccessKeys"
            ],
            "Resource": "*"
        }
    ]
}
```