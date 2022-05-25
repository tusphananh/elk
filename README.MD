# Elasticsearch - Logstash - Kibana

### Feature

### Installation

***
* Install docker, docker-compose
    * [Install docker](https://docs.docker.com/engine/install/ubuntu/)
    * [Install docker-compose](https://docs.docker.com/compose/install/)

* Clone project:

    ~~~
        git clone https://gitlab.com/gcalls-opensource/gcalls-community-version.git
    ~~~

* Grant directory permissions for elasticsearch
    ~~~
        chmod 777 data/es01
    ~~~
* Run docker-compose.yml file
    ~~~
        docker-compose up -d
    ~~~
* Note when installing elk
    * Grant directory permissions for elk
    * Starting elk takes more than 5 minutes and takes 2 - 3 GB of RAM so pay attention to machine resources
* Setting logtash pipeline
    Add output pipeline for fusionpbx missed call with domain name
* Setting password with nginx
    * Config user password with nginx
    * Create user password
        sudo sh -c "echo -n 'gcalls:' >> /etc/nginx/ssl/.htpasswd"
        sudo sh -c "openssl passwd -apr1 >> /etc/nginx/ssl/.htpasswd"
* Add index logtash and index patern
* Setting lua script with pbx 
