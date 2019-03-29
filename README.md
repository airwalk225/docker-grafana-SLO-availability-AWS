# Grafana - Docker

Simple Grafana Docker container to bring up a Grafana instance with provisioned data sources and dashboards/panels.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

You need Docker and Docker compose installed.  
You will also need some AWS credentials for the default CloudWatch data source.

### Installing

Install is pretty easy!


Install Docker and Docker compose on your system
```
https://docs.docker.com/install/
```

For the default data source of CloudWatch, you will need some credentials set up:

```
Log into your AWS account and create a user with the following IAM permissions
(this can be locked down much more!)
CloudWatchEventsReadOnlyAccess - AWS managed policy
CloudWatchLogsReadOnlyAccess - AWS managed policy
CloudWatchReadOnlyAccess - AWS managed policy
```

Collect the access key IF and the secret access key ID and place them into a credentials file as per [this](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html) - Be sure its named default.  
This file will be excluded via the `.gitignore`  
Put this credentials file into `spec/aws`

When you bring the docker container up it will automatically connect to the this data source.  
You can now go and build some dashboards and panaels, save the `json` of the dashboard into `spec/dashboard-items/dashboards`.   
When you rerun the container it will be brough up with your dash board

### Instructions
To bring the container up, in the root directory run `docker-composer up`  
To bring it down `ctrl+c` and then `docker-composer down`  
Go to `localhost:3000` to access the interface, the login is `admin` : `admin`
