# Cloud Run Deployment using Terraform

This module is intended to explain step by step how to easily deploy your application in Google Cloud Run.

## Overview

Cloud Run is a serverless product offered by Google Cloud Platform that allows you to develop and deploy scalable containerized applications.

You can use any programming language you prefer. If you want to know more about Cloud Run, please check the [official documentation](https://cloud.google.com/run)

## Before you begin

- If you do not have one, create a new GCP project in the [Google Cloud Console]() and set up billing on that project.

- [Install Terraform](https://learn.hashicorp.com/tutorials/terraform/install-cli) if you do not have it installed, as it will be needed in order to play with the modules.  
## Authentication

There are **two main ways** to authenticate when using Terraform with the Google provider:

1. The **easiest way** is to authenticate using the `gcloud` command as follows:

```
gcloud auth application-default login
```

[Here](https://cloud.google.com/sdk/gcloud/reference/auth/application-default) you will find further information on the command specified above. 

If you do not have it installed, gcloud can be installed following this [tutorial](https://cloud.google.com/sdk/docs/install). 

2. For a **production use-case**, you will want to use service account authentication, in other words, a [service account](https://cloud.google.com/docs/authentication/getting-started).

From [the service account key page in the Cloud Console](https://console.cloud.google.com/apis/credentials/serviceaccountkey) choose an existing account, or create a new one. 

Download the JSON key file. Name it something you can remember, and **store it somewhere secure on your machine.**

You supply the key to Terraform using the environment variable GOOGLE_APPLICATION_CREDENTIALS, setting the value to the location of the file, as follows:

```
export GOOGLE_APPLICATION_CREDENTIALS={{path}}
```
