FROM debian:latest
MAINTAINER Mans Matulewicz
ENV CONSUL_TEMPLATE_VERSION=0.10.0

RUN apt-get update && apt-get install -y haproxy wget unzip
RUN ( wget --no-check-certificate https://github.com/hashicorp/consul-template/releases/download/v${CONSUL_TEMPLATE_VERSION}/consul-template_${CONSUL_TEMPLATE_VERSION}_linux_amd64.tar.gz -O /tmp/consul_template.tar.gz && gunzip /tmp/consul_template.tar.gz && cd /tmp && tar xf /tmp/consul_template.tar && cd /tmp/consul-template* && mv consul-template /usr/bin && rm -rf /tmp/* )
RUN apt-get clean

COPY haproxy.ctmpl /etc/haproxy.ctmpl
COPY haproxy.json /etc/haproxy.json

EXPOSE 80/tcp 9000/tcp
CMD ["consul-template", "-config=/etc/haproxy.json", "-consul=consul:8500"]