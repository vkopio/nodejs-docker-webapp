# nodejs-docker-webapp

Example app for showing building a simple web app using docker and Jenkins, deploying to Kubernetes, based on https://nodejs.org/en/docs/guides/nodejs-docker-webapp

This service has been used as part of Kubernetes workshop at Unity Helsinki office
## Run locally

Build docker image and run container locally
```
$ docker build --tag nodejs-docker-webapp .
$ docker run --name nodejs-docker-webapp --rm --publish 8080:8080 nodejs-docker-webapp
```

To stop container, start another command prompt and run
```
$ docker stop nodejs-docker-webapp
```

# Deployment to Google Kubernetes Engine

This project is using [CircleCI](https://circleci.com) for building and deploying to Google Kubernetes Engine (GKE). See `.circleci` folder for config.

Following environment variables needs to be defined:

| Environment variable             | Description                                                              | Example                                      |
| -------------------------------- | ------------------------------------------------------------------------ | -------------------------------------------- |
| WORKSHOP_CI_ACCOUNT_TOKEN_BASE64 | Base64 encoded json token for service account with access to GCR and GKE |                                              |
| WORKSHOP_CI_USER                 | Service account user name                                                | `workshop@(project).iam.gserviceaccount.com` |
| WORKSHOP_CLUSTER                 | GKE cluster name                                                         | `workshop-cluster`                           |
| WORKSHOP_CLUSTER_ZONE            | GKE cluster zone                                                         | europe-north1-b                              |
| WORKSHOP_GCP_PROJECT             | GCP Project name                                                         | workshop-test                                |
