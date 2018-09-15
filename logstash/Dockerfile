ARG ELK_VERSION

# https://github.com/elastic/logstash-docker
FROM docker.elastic.co/logstash/logstash:${ELK_VERSION}

USER root

RUN touch /etc/yum.repos.d/mongodb-org-4.0.repo

RUN echo $'[mongodb-org-4.0]\n\
name=MongoDB Repository\n\
baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/4.0/x86_64/\n\
gpgcheck=1\n\
enabled=1\n\
gpgkey=https://www.mongodb.org/static/pgp/server-4.0.asc\n'\
>> /etc/yum.repos.d/mongodb-org-4.0.repo

RUN yum install -y mongodb-org-shell

# Add your logstash plugins setup here
# Example: RUN logstash-plugin install logstash-filter-json
