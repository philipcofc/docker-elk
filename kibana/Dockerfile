FROM kibana:latest

RUN apt-get update && apt-get install -y netcat && apt-get install -y curl

RUN mkdir -p /opt/kibana/config \
    && cd /opt/kibana/config \
    && wget https://raw.githubusercontent.com/philipcofc/docker-elk/magento/kibana/config/kibana.yml

RUN cd /tmp \
    && wget https://raw.githubusercontent.com/philipcofc/docker-elk/magento/kibana/entrypoint.sh \
    && chmod +x /tmp/entrypoint.sh

# Rebuilding container fails, if plugin already exists and try to install
RUN kibana plugin --remove sense \
    && kibana plugin --install elastic/sense

CMD ["/tmp/entrypoint.sh"]
