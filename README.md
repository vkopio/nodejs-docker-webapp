# nodejs-docker-webapp

Example app for showing building a simple web app using docker and Jenkins, deploying to Kubernetes, based on https://nodejs.org/de/docs/guides/nodejs-docker-webapp

Shared Jenkins library used for this demo is in https://github.com/rasmus-unity/shared-jenkinslib-example

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
