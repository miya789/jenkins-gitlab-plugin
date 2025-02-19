# Jenkins GitLab Confirm

## Purpose

- Investigate the conditions that cause permission errors with the `gitlab` plugin.
- If the cause is identified, create an issue.

## Logs

- The container image was outdated, causing an error during plugin installation, so the following command was executed:

```bash
$ docker pull jenkins/jenkins:lts-jdk11
lts-jdk11: Pulling from jenkins/jenkins
cdd62bf39133: Pull complete
21f106ffc421: Pull complete
39df2c5808cf: Pull complete
d9d5ad5daae2: Pull complete
21d9152ebad0: Pull complete
ddc06df74615: Pull complete
bf388b3d4868: Pull complete
1f6fc1ff002b: Pull complete
6201e887d163: Pull complete
a3d60a50862f: Pull complete
282c783b8e01: Pull complete
ddf03cc24103: Pull complete
Digest: sha256:6aa6c6bd7da914bf5333305c8102cb26965ea4b227e37f4269315725a2b0cd81
Status: Downloaded newer image for jenkins/jenkins:lts-jdk11
docker.io/jenkins/jenkins:lts-jdk11

What's Next?
  View summary of image vulnerabilities and recommendations → docker scout quickview jenkins/jenkins:lts-jdk11
```

## HowTo

```bash
docker-compose up --build
```

When finished, run the following command:

```bash
docker rm jenkins-container
```

## ToDo

- Define jobs using Job DSL.
