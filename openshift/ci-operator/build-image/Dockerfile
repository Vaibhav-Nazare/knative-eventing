# Dockerfile to bootstrap build and test in openshift-ci

FROM registry.ci.openshift.org/openshift/release:golang-1.18

# Add kubernetes repository
ADD openshift/ci-operator/build-image/kubernetes.repo /etc/yum.repos.d/

RUN yum install -y kubectl httpd-tools

RUN GOFLAGS='' go install github.com/mikefarah/yq/v3@latest

# Allow runtime users to add entries to /etc/passwd
RUN chmod g+rw /etc/passwd
