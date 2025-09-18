I have configured docker-compose.yml to start elasticsearch and kibana containers.
Run "docker compose up -d" to start elasticsearch and kibana containers.

To start Logstash container:
docker run -d --name logstash --network elk_stack_elastic -p 5044:5044 -p 5000:5000 -v /elk_stack/logstash:/usr/share/logstash/pipeline -v /elk_stack/logstash/config/logstash.yml:/usr/share/logstash/config/logstash.yml   docker.elastic.co/logstash/logstash:7.17.27
. # docker logs logstash -f

Comamnds:
curl -X GET "http://elasticsearch:9200/_cat/indices?v"
curl -X GET "http://10.15.1.170:9200/_cat/indices/nis-accountnu-*?v"

Requirements to connect Oracle database with Elasticsearch:
=> Download ojdbc8.jar and write oracle_jdbc_test.conf pipeline like shown in this repo to connect with database.
Requirement from Oracle database: 
1. Oracle Host and port
2. service name
3. DB user and password
4. Table name and SQL Query

Make configuration as shown in this repo and you will easily connect oracle with elasticsearch.





