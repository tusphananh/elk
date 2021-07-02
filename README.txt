1. Generate certificates for Elasticsearch by bringing up the create-certs container:

docker-compose -f create-certs.yml run --rm create_certs

2. Bring up the three-node Elasticsearch cluster:
 
docker-compose -f elastic-docker-tls.yml up -d

3. Run the elasticsearch-setup-passwords tool to generate passwords 
for all built-in users, including the kibana_system user. 
If you don’t use PowerShell on Windows, remove the trailing `\`characters 
and join the lines before running this command:

docker exec es01 /bin/bash -c "bin/elasticsearch-setup-passwords \
auto --batch --url https://es01:9200"

--> Save all the passwords and user information to another environment

4. Set ELASTICSEARCH_PASSWORD in the elastic-docker-tls.yml compose file 
to the password generated for the kibana_system user.

5. Use docker-compose to restart the cluster and Kibana:
docker-compose stop
docker-compose -f elastic-docker-tls.yml up -d

6. Open Kibana to load sample data 
and interact with the cluster: https://localhost:5601 (Required https)