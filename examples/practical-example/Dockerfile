FROM jcsilva/docker-kaldi-gstreamer-server
MAINTAINER Eduardo Silva <zedudu@gmail.com>

# This is the practical example part

RUN apt-get update && \
    apt-get install -y supervisor && \
    rm -rf /var/lib/apt/lists/*

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

RUN mkdir -p /opt/models
COPY tdnn_7b_chain_online /opt/models/tdnn_7b_chain_online

COPY config.yaml /opt/models/config.yaml

EXPOSE 80

CMD ["/usr/bin/supervisord"]
