# My website

Site is live here: https://www.simonolander.org

#### Install

```shell script
yarn install
```

#### Run locally

```shell script
yarn start
```

#### Increment patch version and release

```shell script
yarn patch
```

#### Ionicons

For browsing: https://ionic.io/ionicons/v4

## Hosting

The site is hosted on AWS, in an S3 bucket. Apart from the release script in [create-release.yml](.github/workflows/create-release.yml), the following setup had to take place:

1. Create an S3-bucket
2. Enable static website hosting
3. Create an IAM user
4. Grant the user these permissions:
```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "",
            "Effect": "Allow",
            "Action": [
                "s3:PutObject",
                "s3:PutObjectAcl",
                "s3:GetObject",
                "s3:ListBucket",
                "s3:DeleteObject",
                "s3:GetBucketLocation"
            ],
            "Resource": [
                "arn:aws:s3:::YOUR_BUCKET",
                "arn:aws:s3:::YOUR_BUCKET/*"
            ]
        }
    ]
}
```
6. Add the user's credentials GitHub Secrets