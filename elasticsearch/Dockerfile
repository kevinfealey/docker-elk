FROM elasticsearch:5

COPY ./config/elasticsearch.yml /etc/elasticsearch/elasticsearch.yml
COPY ./config/elasticsearch.yml /usr/share/elasticsearch/config/elasticsearch.yml
ENV ES_JAVA_OPTS="-Des.path.conf=/etc/elasticsearch"

CMD ["-E", "network.host=0.0.0.0", "-E", "discovery.zen.minimum_master_nodes=1"]
