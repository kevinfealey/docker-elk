FROM kibana:5

RUN apt-get update && apt-get install -y netcat bzip2

RUN chmod +x /tmp/entrypoint.sh

CMD ["/tmp/entrypoint.sh"]
