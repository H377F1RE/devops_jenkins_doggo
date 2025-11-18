FROM jenkins/jenkins:alpine

USER root
RUN apk update && apk add docker-cli docker-compose && \
    addgroup -S docker || true && \
    addgroup jenkins docker

USER jenkins
