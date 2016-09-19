FROM logstash:latest

RUN mkdir -p /etc/logstash/conf.d \
    && cd /etc/logstash/conf.d \
    && curl -O https://raw.githubusercontent.com/philipcofc/docker-elk/magento/logstash/config/logstash.conf

# Install filebeats plugin for logstash
RUN logstash-plugin install logstash-input-beats