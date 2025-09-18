I have configured docker-compose.yml to start elasticsearch and kibana containers.
Run "docker compose up -d" to start elasticsearch and kibana containers.

To start Logstash container:
docker run -d --name logstash --network elk_stack_elastic -p 5044:5044 -p 5000:5000 -v /elk_stack/logstash:/usr/share/logstash/pipeline -v /elk_stack/logstash/config/logstash.yml:/usr/share/logstash/config/logstash.yml   docker.elastic.co/logstash/logstash:7.17.27




