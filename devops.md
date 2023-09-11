# DevOps

## Front-end

For the Front-end we don't need a hosting setup, Because all these things are handled by the jira Itself\
\
Command for deployment:

```
forge deploy -e production // for production purpose
```

This is handled in deployment pipeline, when a commit is pushed to dev branch, it will be deployed to development environment, the same will be applied to staging and main when it reaches the staging branch,and main branch



## Back-end

#### The Back-end  is hosted on AWS(amazon web service)

Currently we are using Amazon Elastic Container Service (ECS) for production environment and an Amazon Elastic Compute Cloud (Amazon EC2) for the development environment and these are created using terraform\
\
This is also handled by the pipeline setup similar to Front-end and the corresponding branches are dev for development, staging for staging and master for production\
\
We are currently running pytest on the development branch, so if there is any error, the deployment will fail&#x20;
