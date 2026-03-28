# My website

Site is live here: https://www.simonolander.org

#### Install

```shell script
npm run install
```

#### Run locally

```shell script
npm run dev
```

#### Release

```shell script
npm run release
```

#### Ionicons

For browsing: https://ionic.io/ionicons/v4

## Hosting

The site is hosted on AWS, in an S3 bucket. Apart from the release script in [create-release.yml](.github/workflows/create-release.yml), the following resources need to be created in AWS:

* An S3 bucket for hosting
* An IAM user for CICD
* A certificate for TLS
* A CloudFront distribution

The IAM user's credentials must be added to Github Secrets.