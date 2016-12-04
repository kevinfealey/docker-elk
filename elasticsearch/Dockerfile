FROM elasticsearch:5

COPY ./config/elasticsearch.yml /etc/elasticsearch/elasticsearch.yml
COPY ./config/elasticsearch.yml /usr/share/elasticsearch/config/elasticsearch.yml
ENV ES_JAVA_OPTS="-Des.path.conf=/etc/elasticsearch"

#Required when mapping the data volume to another unix system (confirmed with Ubuntu), 
#especially when the host is a VM and VBoxfs is used. Otherwise the data folder will 
#be owned by 1000 (or potentially another uid - in which case, update the number 
#in the following line), and the elasticsearch user in the container will not have access.
RUN ["/bin/bash", "-c", "usermod -u 1000 elasticsearch"]

CMD ["-E", "network.host=0.0.0.0", "-E", "discovery.zen.minimum_master_nodes=1"]
