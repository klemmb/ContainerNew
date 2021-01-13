# Containers in 3 weeks — Week 1 setup

## Installation

You will need Docker installed! 
Here is a [link](https://docs.docker.com/get-docker/) to get you started.
Proceed after you are done installing.

## Warm up your engines!

Using the command (bash) prompt:

```bash
docker pull alpine:3.12;
docker pull jenkins/jenkins:2.99;
docker pull mongo:3.6.17;
docker pull nginx:1.19.6-alpine;
docker pull openjdk:8u131-jdk;
docker pull openjdk:8u131-jre;
docker pull portainer/portainer:latest;
docker pull tomcat:9;
docker pull ubuntu:21.04;
```

## The final test

Once again, at the command prompt:

```bash
> docker run -d --name myjenkins -p 8080:8080 jenkins/jenkins:2.99;
> docker logs -f myjenkins;
```

You should see the Jenkins logs flowing by eventually settling with the following:

```
Sep 18, 2018 11:38:19 PM hudson.model.UpdateSite updateData
INFO: Obtained the latest update center data file for UpdateSource default
Sep 18, 2018 11:38:19 PM hudson.WebAppMain$3 run
INFO: Jenkins is fully up and running
Sep 18, 2018 11:38:19 PM hudson.model.UpdateSite updateData
INFO: Obtained the latest update center data file for UpdateSource default
Sep 18, 2018 11:38:20 PM hudson.model.DownloadService$Downloadable load
INFO: Obtained the updated data file for hudson.tasks.Maven.MavenInstaller
Sep 18, 2018 11:38:20 PM hudson.model.DownloadService$Downloadable load
INFO: Obtained the updated data file for hudson.tools.JDKInstaller
Sep 18, 2018 11:38:20 PM hudson.model.AsyncPeriodicWork$1 run
INFO: Finished Download metadata. 7,798 ms
--> setting agent port for jnlp
--> setting agent port for jnlp... done
```

Visit http://localhost:8080 and see if you see the Jenkins login page.
If you do, you are all set to go!!

```bash
# ctrl-c to break out of the logs
docker container stop myjenkins;
docker container rm myjenkins;
```

Woot!!!
