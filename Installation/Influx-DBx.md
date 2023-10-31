# Installation of influx DB using docker :
    docker run -d -p 8086:8086 --name influxdb2 influxdb:1.8.6-alpine

# Installation using documentation :
    1. For Ubuntu/Debian users, add the InfluxData repository with the following commands:
       wget -q https://repos.influxdata.com/influxdata-archive_compat.key
       echo '393e8779c89ac8d958f81f942f9ad7fb82a25e133faddaf92e15b16e6ac9ce4c influxdata-archive_compat.key' | sha256sum -c && cat influxdata-archive_compat.key | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/influxdata-archive_compat.gpg > /dev/null
       echo 'deb [signed-by=/etc/apt/trusted.gpg.d/influxdata-archive_compat.gpg] https://repos.influxdata.com/debian stable main' | sudo tee /etc/apt/sources.list.d/influxdata.list

    2. Then, install and start the InfluxDB service :
       sudo apt-get update && sudo apt-get install influxdb
       sudo service influxdb start

# Influx DB with Jenkins :
    1. First install Influx DB 
    2. Create an database in Influx DB for jenkins as 
         docker exec -it influxdb2 bash   # If you are using docker container for Influx DB
         influx
         CREATE DATABASE "jenkins" WITH DURATION 1825d REPLICATION 1 NAME "jenkins-retention"
         SHOW DATABASES
         USE <database_name>
    3. Now in jenkins install the plugin for Influx DB & then go to configure and add all data related to Influx DB.

